# microservices

- https://github.com/PacktPublishing/Hands-On-Microservices-with-Spring-Boot-and-Spring-Cloud

## local

### build
```cmd
./grdelw clean build
```

### test
```cmd
./test-em-all.bash
```

## docker 

### build and run
```cmd
./grdelw clean build
docker-compose build
docker-compose up -d
```

### log
```cmd
docker-compose logs -f
docker-compose logs -f product review
```

### error
```cmd
# disk error
docker system prune -f --volumes

# restart service
docker-compose up -d --scale product=0
docker-compose up -d --scale product=1 
```

### test with docker
```cmd
./test-em-all.bash start stop
```

### check
- java SE 10 이상 사용
    - 그 이하 버전에서는 리소스 제한이 안됨.
    
## Continuous Integration

### build and test
```cmd
./grdelw clean build && docker-compose build && ./test-em-all.bash start stop
```