# ---- Base : dépendances communes aux autres stages ----
FROM node:20-alpine AS base
WORKDIR /app
COPY package*.json ./

# ---- Dev : hot reload avec le serveur Vite ----
FROM base AS dev
RUN npm install
COPY . .
EXPOSE 5173
CMD ["npm", "run", "dev", "--", "--host"]

# ---- Build : compile les assets statiques ----
FROM base AS build
RUN npm install
COPY . .
RUN npm run build

# ---- Production : assets statiques servis par Nginx ----
FROM nginx:alpine AS production
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
