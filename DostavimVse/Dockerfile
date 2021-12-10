FROM maven:3.8.2-jdk-8

WORKDIR /mavenapp

COPY . /mavenapp

RUN mvn clean install package -Dstart-class=ru.fivt.dostavimvse.DostavimvseApplication
RUN cp /mavenapp/target/dostavimvse-0.0.1-SNAPSHOT.jar /mavenapp/DostavimvseApplication.jar


RUN mvn clean install package -Dstart-class=Main
RUN cp /mavenapp/target/dostavimvse-0.0.1-SNAPSHOT.jar Main.jar

CMD java -jar /mavenapp/Main.jar & java -jar /mavenapp/DostavimvseApplication.jar