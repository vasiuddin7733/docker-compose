FROM node:16 as build-stage
WORKDIR /backend
COPY package.json package-lock.json
RUN npm install

FROM alpine:latest as production-stage
COPY --from=build-stage /backend/dist /backend
VOLUME [ "/backend" ]