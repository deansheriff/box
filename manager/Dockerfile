FROM node:20-slim

WORKDIR /app

COPY package.json package-lock.json* ./
RUN npm install

COPY . .

# Skip TS type checking and ESLint during build
ENV NEXT_TELEMETRY_DISABLED=1
ENV NODE_OPTIONS=--max-old-space-size=4096

RUN npm run build -- --no-lint

EXPOSE 3000

CMD ["npm", "start"]