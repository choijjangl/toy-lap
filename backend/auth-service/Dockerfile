FROM eclipse-temurin:21-jdk
WORKDIR /app

COPY build/libs/auth-service-0.0.1-SNAPSHOT.jar app.jar
# 그래들로 빌드시.

# jar파일로 실행
ENTRYPOINT ["java", "-jar", "app.jar"]