## Install Airflow in MAC M2 by Docker

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

airflow/
├── dags/
├── logs/
├── plugins/
├── config/
└── cicd/
    ├── Dockerfile
    └── docker-compose.yaml


