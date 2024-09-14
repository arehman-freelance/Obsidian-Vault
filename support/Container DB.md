## Installation

Install docker. Read docker official installation documentation.

[https://docs.docker.com/engine/install/centos/](https://docs.docker.com/engine/install/centos/)

## Setup new Instance

- Create folder at home as per customer name/customer id
    
- Create docker compose file docker-compose.yaml
    

```yml
services:
  oracledb:
    image: 'container-registry.oracle.com/database/free:latest'
    restart: unless-stopped
    ports:
      - '1521:1521'
    environment:
      - ORACLE_SID=FREE
      - ORACLE_PDB=FREEPDB1
      - ORACLE_PWD=Force0321
    volumes:
      - ./oradata:/opt/oracle/oradata
      - /home/container1/public_html:/opt/sulemandb
      - /home/oracle/wallet:/home/oracle/wallet
    deploy:
      resources:
        limits:
          memory: 3g
          cpus: '2.0'

  ords:
    image: container-registry.oracle.com/database/ords-developer:latest
    volumes:
      - ./ords_secrets/:/opt/oracle/variables
      - ./ords_config/:/etc/ords/config/
      - ./entrypoint.sh:/entrypoint.sh
      #environment:
      #- JAVA_OPTIONS=-Xms512m -Xmx1024
    restart: unless-stopped
    ports:
      - '127.0.0.1:8181:8181'
    deploy:
      resources:
        limits:
          memory: '1g'
          cpus: '1.5'
```

- copy entrypoint.sh file
    
- create folders
    
    - oradata
        
    - ords_config
        
    - ords_secrets
        
- create conn_string.txt file in ords_secrets with content
    

```
CONN_STRING=sys/Force0321@oracledb:1521/FREEPDB1
```

## Run containers

```bash
docker compose up -d oracledb
docker compose up -d ords
```

==First time it takes time to deploy. So first wait and check logs of oracledb container if container started then only start ords container.==




