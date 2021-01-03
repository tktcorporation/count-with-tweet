FROM rust:1.48-buster

RUN apt-get update
RUN apt-get install -y build-essential openjdk-11-jre graphviz plantuml

RUN java -jar /usr/share/plantuml/plantuml.jar -h

WORKDIR /app

COPY ./book.toml .

RUN cargo install mdbook
# RUN cargo install mdbook-graphviz
RUN cargo install mdbook-plantuml --no-default-features

CMD [ "/bin/sh", "-c", "mdbook serve --hostname '0.0.0.0'" ]