# ---- Base : dépendances communes aux autres stages ----
FROM node:20-alpine AS base
WORKDIR /app
COPY package*.json ./

# ---- Dev : hot reload avec nodemon ----
FROM base AS dev
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npx", "nodemon", "--legacy-watch", "index.js"]

# ---- Build : installe uniquement les dépendances de production ----
FROM base AS build
RUN npm ci --omit=dev

# ---- Production : image finale allégée (sans devDependencies ni outils de dev) ----
FROM node:20-alpine AS production
WORKDIR /app
COPY --from=build /app/node_modules ./node_modules
COPY package*.json ./
COPY . .
EXPOSE 3000
CMD ["node", "index.js"]
