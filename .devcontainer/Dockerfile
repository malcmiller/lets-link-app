FROM node:18

RUN curl -s https://ngrok-agent.s3.amazonaws.com/ngrok.asc | \
    tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null && \
    echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | \
    tee /etc/apt/sources.list.d/ngrok.list && \
    apt update && apt install ngrok

# Install global npm packages
RUN npm install -g npm@latest
RUN npm install -g eslint typescript expo-cli @expo/ngrok@^4.1.0
RUN node --version && npm --version