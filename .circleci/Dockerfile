FROM cimg/node:14.18

RUN sudo apt-get update && sudo apt-get install -y python3.8 python-is-python3 python3.8-venv
RUN cd ~/ \
    && curl "https://s3.amazonaws.com/aws-cli/awscli-bundle.zip" -o "awscli-bundle.zip" \
    && unzip awscli-bundle.zip \
    && sudo ~/awscli-bundle/install -i /usr/local/aws -b /usr/local/bin/aws \
    && rm -rf awscli-bundle awscli-bundle.zip
RUN cd ~/ \
    && curl "https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-linux-x86_64.zip" -o "aws-sam-cli-linux.zip" \
    && unzip aws-sam-cli-linux.zip -d sam-installation \
    && sudo ./sam-installation/install \
    && rm -rf sam-installation aws-sam-cli-linux.zip

CMD ["/bin/sh"]