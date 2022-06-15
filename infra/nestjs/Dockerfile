ARG NODE_IMAGE=node:16.15.1-alpine

FROM $NODE_IMAGE AS base
RUN apk --no-cache add dumb-init
RUN mkdir -p /var/www/backend && chown node:node /var/www/backend
WORKDIR /var/www/backend
USER node
RUN mkdir tmp

FROM base AS dependencies
COPY --chown=node:node package.json yarn.lock ./
RUN yarn install
COPY --chown=node:node . .

FROM dependencies AS build
RUN yarn build

FROM base AS production
ENV NODE_ENV=production
ENV PORT=$PORT
ENV HOST=0.0.0.0
COPY --chown=node:node ./package*.json ./
RUN yarn install --production
COPY --chown=node:node --from=build /var/www/backend/dist .
EXPOSE $PORT
CMD ["dumb-init", "node", "dist/main"]