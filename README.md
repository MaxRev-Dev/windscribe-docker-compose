# Windscribe + UaShield Compose
 
**ALERT** - I'm not supporting unlawful active attack or malware campaings that are causing technical harms. Use it only for educational purposes. You can only try this platform on your own website!
  
### This docker-compose file contains:
- [Windscribe VPN](https://windscribe.com/) 
- [NoWarDDoS](https://gitlab.com/a_gonda/nowarddos) 
- [UaShield](https://github.com/opengs/uashield)

You can add your own service as show below:
```
  service_name: # unique service name
    image: service_image_source # image source on hub
    restart: unless-stopped
    depends_on: 
      - docker-windscribe
    network_mode: "service:docker-windscribe"
```

### How to use it:
1. Update variables WINDSCRIBE_USERNAME and WINDSCRIBE_PASSWORD in`.env.dev` to your values.
2. Rename `.env.dev` to `.env`
3. Simply run docker-compose
    `docker-compose up -d --pull=always`
    Or where --scale sets number of intances of specific service
    `docker-compose up -d --pull=always --scale uashield=2 --scale nowarddos=2`