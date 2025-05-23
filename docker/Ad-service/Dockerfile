FROM eclipse-temurin:21-jdk AS builder

WORKDIR /usr/docker/Ad-service/

COPY gradlew* settings.gradle* build.gradle .
COPY ./gradle ./gradle

RUN chmod +x ./gradlew
RUN ./gradlew
RUN ./gradlew downloadRepos

COPY . .
COPY ./pb ./proto
RUN chmod +x ./gradlew
RUN ./gradlew installDist -PprotoSourceDir=./proto

#####################################################

FROM eclipse-temurin:21-jre

WORKDIR /usr/docker/Ad-service/

COPY --from=builder /usr/docker/Ad-service/ ./

ENV AD_PORT 9099

ENTRYPOINT ["./build/install/e-commerce-open-telemetry-project-Ad-service/bin/Ad-service"]
