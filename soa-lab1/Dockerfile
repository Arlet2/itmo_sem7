FROM alpine/git:2.45.2 as BUILD

RUN git clone https://github.com/swagger-api/swagger-ui.git

FROM node:22-alpine3.19 as RUN

COPY --from=build /git/ /

WORKDIR swagger-ui

COPY swag/ dev-helpers/

RUN npm install

ENTRYPOINT ["npm", "run", "dev"]