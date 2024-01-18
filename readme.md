Experimenting faster and effecient docker builds for projects including tensorflow ( which is large ).

## Method 1 (Not recommended)
Manual installation of tensorflow as a python package.
- Not implemented

## Method 2 (Recommended)

Using docker hub tensorflow docker images as base images.

Example:
```dockerfile

FROM tensorflow/tensorflow:latest-gpu

# Add your application here

```

REF: https://hub.docker.com/r/tensorflow/tensorflow/

Tested tags:

- [latest tag](./tensor-flow-base-images/latest/)
- [latest gpu tag](./tensor-flow-base-images/latest-gpu/)
- [nightly tag](./tensor-flow-base-images/nightly/)
- [nightly gpu tag](./tensor-flow-base-images/nightly-gpu/)

# Limitations
- The base images are large. So, the final image size will be large.
- The base images are large. So, the builds will take reasonable time.
- The base images are large. So, the docker hub pulls will take reasonable time.
- No application is added to the base images. So, build time may vary depending on the application.

# Observations
- Using docker hub tensorflow images as base images is fast ( Not tested Manual installation of tensorflow as a python package. ). Since the base images are already built and available in docker hub. Builds take reasonable time.
  - [latest tag](./tensor-flow-base-images/latest/)
    - 37s
  - [latest gpu tag](./tensor-flow-base-images/latest-gpu/)
    - 1m 0s
  - [nightly tag](./tensor-flow-base-images/nightly/)
    - 24s
  - [nightly gpu tag](./tensor-flow-base-images/nightly-gpu/)
    - 1m 7s

# Disclaimer
- All runs are done in Github Actions.