# ESPHome Device Builder (custom development build)

This add-on flavor uses the unique slug `esphome-dev-custom` and the image
`ghcr.io/schinckel/esphome-hassio-packages`. It can be installed alongside
the official add-ons after that custom image is published for the same
architectures.

The add-ons use host networking and ESPHome listens on port 6052, so only one
Device Builder add-on can run at a time. The image workflow builds the frontend
and backend wheels from the `packages-editor` branches, layers them over the
official ESPHome HA image, and publishes the multi-architecture image to GHCR.

After the image is public, add the `schinckel/home-assistant-addon` repository
to the Home Assistant app store and install this app. Stop the other ESPHome
Device Builder app before starting this one.
