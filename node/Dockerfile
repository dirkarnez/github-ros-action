FROM ros:noetic-ros-base

RUN apt-get update &&\
    apt-get install -y \
        net-tools \
        iputils-ping \
        dnsutils \
        nano && \
    rm -rf /var/lib/apt/lists/*

COPY check-roscore.py /usr/local/bin/check-roscore.py
COPY entrypoint.sh /usr/local/bin/entrypoint.sh
COPY wait-for-it.sh /usr/local/bin/wait-for-it.sh

RUN chmod 755 /usr/local/bin/check-roscore.py &&\
    chmod 755 /usr/local/bin/entrypoint.sh &&\
    chmod 755 /usr/local/bin/wait-for-it.sh

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
CMD ["bash"]
