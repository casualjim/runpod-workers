ARG BASE_IMAGE_FLAVOR=86-1.6

FROM ghcr.io/huggingface/text-embeddings-inference:${BASE_IMAGE_FLAVOR}

RUN apt-get update && apt-get install -y \
    libssl-dev \
    pkg-config \
    supervisor

COPY supervisord.conf /etc/supervisor/supervisord.conf

EXPOSE 8000 8001
ENTRYPOINT ["/usr/bin/supervisord"]
CMD ["-c", "/etc/supervisor/supervisord.conf"]