FROM brewblox/brewblox-service:latest

# Bit of a trick: copy Dockerfile, and the "pkg" directory if it exists
# This allows a conditional copy of ./pkg/*
RUN mkdir -p /pkg
COPY ./Dockerfile ./pkg/* /pkg/

EXPOSE 5000

RUN pip3 install /pkg/* || true \
    && pip3 install brewblox-devcon-spark \
    && pip3 show brewblox-devcon-spark

ENTRYPOINT ["python3", "-m", "brewblox_devcon_spark"]
