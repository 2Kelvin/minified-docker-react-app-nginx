# Minified React App Nginx

Minifying a react app and running the minimal build to be served by nginx docker container

## Multi-stage dockerfile
In the first stage `react_build`, that's where all the heavy building of the app is happening, which ends with a production levl build folder. In stage 2 `web_server`, I copied the build folder from **react_build** into this stage to be served by the `Nginx` container.

I reduced the final image by 88%. The original **react_build image** image size was 775.3 mb but the final **web_server image** with nginx installed was 94.16 mb.

pushed the image to docker hub
```bash
docker push rocketman02/mini_react_web:v1
```