
FROM openjdk:11

RUN apt-get update
RUN apt-get install -y git
RUN git clone https://github.com/barais/doodlestudent.git
WORKDIR /app/doodlestudent/api

RUN ./mvnw package -Dmaven.test.skip=true
EXPOSE 8080
CMD ["java", "-jar", "target/tlcdemoApp-1.0.0-SNAPSHOT-runner.jar"]