# YetiCTF Quals Deploy

## Using
### 0. Clone this repo with submodules
```bash
git clone --recurse-submodules https://github.com/n57uctf/yetictf-quals-deploy
```

### 1. Prepare `.env` file
```bash
htpasswd -n ctf # to generate Traefik Dashboard password
cp .env.sample .env
vi .env # provide generated string to TRAEFIK_BASICAUTH variable
```

### 2. Prepare `.school.env` and `.student.env` file
```bash
cp .student.env.sample .student.env
cp .school.env.sample .school.env
vi .student.env # Change all default credentials and provide S3 key id and key secret for backing up
vi .school.env # Change all default credentials and provide S3 key id and key secret for backing up
```

### 3. Run docker-compose
```bash
docker-compose up -d
```
Docker containers:
```
quals_school_cache_1
quals_frontpage_1
quals_student_db_1
quals_school_db_1
quals_student_cache_1
quals_student_ctfd_1
quals_school_ctfd_1
quals_student_db_backup_1
quals_traefik_1
```
