FROM node:22-alpine

#inside container where making app folder
WORKDIR /app

#copying all the dependencies file
COPY package.json ./

RUN npm install

#copying everything to app folder
COPY . .

#setting environment variable for api url
ARG VITE_API_URL
ENV VITE_API_URL=$VITE_API_URL

# Fix esbuild version mismatch by reinstalling
RUN npm uninstall esbuild && npm install esbuild

RUN npm run build

EXPOSE 5173

CMD ["npm", "run", "preview"]