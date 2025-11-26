## Install Airflow 3.0 in MAC M2 by Docker

### 1. install homebrew
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
### 2. check brew version
berw --version 

<img width="376" height="27" alt="스크린샷 2025-11-26 오후 2 09 14" src="https://github.com/user-attachments/assets/18816381-1ee5-4efa-a386-5d2078922bb0" />

### 3. install colima
brew install colima

<img width="363" height="32" alt="스크린샷 2025-11-26 오후 2 18 25" src="https://github.com/user-attachments/assets/45affaa4-8b3e-4a7a-8ab3-150d96477d21" />

colima start --arch aarch64 --cpu 4 --memory 8 --disk 60

<img width="669" height="255" alt="스크린샷 2025-11-26 오후 2 20 42" src="https://github.com/user-attachments/assets/9109cf32-9fcc-453d-85cb-18685ca6e3ba" />

### 4. check docker version
brew install docker-compose
docker --version
docker-compose --version

<img width="579" height="64" alt="스크린샷 2025-11-26 오후 2 23 50" src="https://github.com/user-attachments/assets/17606797-ddd5-4e71-903e-6d63e8ede5ea" />

### 5. airflow docker build 
```bash
airflow/
├── dags/
├── logs/
├── plugins/
├── config/
└── cicd/
    ├── Dockerfile
    └── docker-compose.yaml
```

mkdir airflow
cd airflow
mkdir -p ./dags ./logs ./plugins ./config
cd cicd 
echo -e "AIRFLOW_UID=$(id -u)" > .env
cd ..

docker-compose -f cicd/docker-compose.yaml build

<img width="846" height="164" alt="스크린샷 2025-11-26 오후 3 16 16" src="https://github.com/user-attachments/assets/5cbc9510-dfad-49c8-80de-9bf12b7d2d2f" />

docker-compose -f cicd/docker-compose.yaml up airflow-init

<img width="830" height="249" alt="스크린샷 2025-11-26 오후 3 18 30" src="https://github.com/user-attachments/assets/4e77eff9-0d0b-4518-8cbc-817d46182b1a" />


docker-compose -f cicd/docker-compose.yaml up -d

<img width="848" height="151" alt="스크린샷 2025-11-26 오후 3 19 55" src="https://github.com/user-attachments/assets/f54ad5bd-e1b2-45bb-988e-e28aa8afd0c4" />


### 6. check airflow webserver

http://localhost:8080/

<img width="1512" height="982" alt="스크린샷 2025-11-26 오후 3 25 55" src="https://github.com/user-attachments/assets/2f929028-ff82-4f57-b836-56cf26dcec7d" />


