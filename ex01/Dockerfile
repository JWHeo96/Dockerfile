FROM openjdk:11-jdk-slim

WORKDIR /app

# ADD 압축파일.zip ./ # 이렇게 하면 압축이 풀린다.
COPY build/aws-v3-0.0.3.jar ./application.jar

# 무조건 실행할 명령어
ENTRYPOINT ["java", "-jar", "-Dspring.profiles.active=dev", "application.jar"]

# 옵션(대체 가능함)
CMD ["--server.port=3000"]