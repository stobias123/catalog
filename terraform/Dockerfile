FROM alpine:latest
RUN apk add wget unzip 
RUN wget https://releases.hashicorp.com/terraform/0.12.3/terraform_0.12.3_linux_amd64.zip && \
    unzip *.zip && mv terraform /bin/ && rm *.zip
ENTRYPOINT ["terraform"]
