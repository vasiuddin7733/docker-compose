FROM node:16 as build-stage
WORKDIR /frontend
COPY package.json package-lock
RUN npm install
COPY ./ .

RUN npm run build

FROM alpine:latest as production-stage
COPY --from=build-stage /frontend/dist /frontend
VOLUME [ "/frontend" ]