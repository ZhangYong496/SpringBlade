# 网络问题无法下载可以改为阿里云镜像
# FROM registry.cn-hangzhou.aliyuncs.com/bladex-repo/alpine-java:openjdk17_cn_slim
FROM bladex/alpine-java:openjdk17_cn_slim

MAINTAINER bladejava@qq.com

RUN mkdir -p /blade/auth

WORKDIR /blade/auth

EXPOSE 8010

ADD ./target/blade-auth.jar ./app.jar

ENTRYPOINT ["java", "--add-opens", "java.base/java.lang=ALL-UNNAMED", "--add-opens", "java.base/java.lang.reflect=ALL-UNNAMED", "-Djava.security.egd=file:/dev/./urandom", "-jar", "app.jar"]

CMD ["--spring.profiles.active=test"]
