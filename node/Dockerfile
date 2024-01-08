FROM ubuntu

RUN apt update && apt install python build-essential gcc g++ git

RUN git clone https://github.com/nodejs/node.git nodejs

WORKDIR /nodejs

RUN ./configure
RUN amake -j 4
RUN make install

ENTRYPOINT [ "/usr/local/bin/node" ]
CMD [ "-e", "console.('hello', process.version)" ]