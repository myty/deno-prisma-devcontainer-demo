ARG VARIANT=bullseye
FROM --platform=linux/amd64 mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}
ARG DENO_VERSION=1.27.0

ENV DENO_INSTALL=/deno
RUN mkdir -p /deno \
    && curl -fsSL https://deno.land/x/install/install.sh | sh -s v$DENO_VERSION \
    && chown -R vscode /deno

ENV VOLTA_HOME=/volta
RUN mkdir -p /volta \
    && curl https://get.volta.sh | bash -s -- --skip-setup \
    && chown -R vscode /volta

ENV PATH=${VOLTA_HOME}/bin:${DENO_INSTALL}/bin:${PATH} \
    DENO_DIR=${DENO_INSTALL}/.cache/deno