# Windscribe + UaShield Compose
 
**ALERT** - I'm not supporting unlawful active attack or malware campaings that are causing technical harms. Use it only for educational purposes. You can only try this platform at your own website!

#### An easy way to deploy some services like UaShield, NoWarDDoS to VPS and AWS platforms.  

## This docker-compose file contains:
- [Windscribe VPN](https://windscribe.com/) 
- [NoWarDDoS](https://gitlab.com/a_gonda/nowarddos) 
- [UaShield](https://github.com/opengs/uashield)

#### You can add your own service as show below:
```
  service_name: # unique service name
    image: service_image_source # image source on hub
    restart: unless-stopped
    depends_on: 
      - docker-windscribe
    network_mode: "service:docker-windscribe"
```

## How to use it:
Prerequisites (you will need): `docker` and `docker-compose`.
Also Windscribe **account is required**. The best solution is to buy a custom plan where **`$2 for Russian Location + $2 for unlimited trafic`**

1. Update variables WINDSCRIBE_USERNAME and WINDSCRIBE_PASSWORD in`.env.dev` to your values.
2. Rename `.env.dev` to `.env`
3. Simply run docker-compose
    `docker-compose up -d --pull=always`

    If more resources are available you can scale services. Use --scale to set number of intances of a specific service
    `docker-compose up -d --pull=always --scale uashield=2 --scale nowarddos=2`

## Donations
This project is provided with the best wishes to protect our country - Ukraine.
We do not need donations but you can to Armed Forces of Ukraine or humanitarian needs.
See more at https://standforukraine.com/