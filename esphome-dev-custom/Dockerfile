ARG BASE_IMAGE=ghcr.io/esphome/esphome-hassio:dev
FROM ${BASE_IMAGE}

COPY wheels/ /tmp/device-builder-wheels/

RUN uv pip install --system \
      --no-cache-dir \
      --no-deps \
      --force-reinstall \
      /tmp/device-builder-wheels/*.whl \
    && rm -rf /tmp/device-builder-wheels

ARG BUILD_VERSION=dev
LABEL \
    io.hass.name="ESPHome Device Builder (custom dev)" \
    io.hass.description="ESPHome Device Builder with the Packages editor" \
    io.hass.type="addon" \
    io.hass.version="${BUILD_VERSION}"
