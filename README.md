Bring custom_component
=========================

This is a custom component for home-assistant to track bring packages.

Its activated by adding the following to your configuration.yaml:
```yaml
sensor:
  - platform: bring
```

After that you can start to track your packages by calling the service
`bring.register`  with a argument looking like
`{"package_id": "12345678"}` to have home-assistant start tracking
that package.

And when you loose interest in that package, you just stop tracking it by
calling `bring.unregister` with a corresponding argument.


To view all your packages in a nice fashion, I use the auto-entities[1]
card to view them all as a list in lovelace:
```yaml
      - card:
          type: entities
        filter:
          include:
            - domain: bring
        type: 'custom:auto-entities'
```

This component shares quite a bit of code and architecture
with my package tracker for Postnord[2] and DHL[3].


1. https://github.com/thomasloven/lovelace-auto-entities
2. https://github.com/glance-/postnord
2. https://github.com/glance-/dhl
