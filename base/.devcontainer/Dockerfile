FROM node

RUN apt-get update && \
  apt-get install -y awscli fish && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

RUN curl -sS https://starship.rs/install.sh | sh -s -- -y

USER node

RUN mkdir -p ~/.config/fish && echo 'starship init fish | source' >> ~/.config/fish/config.fish

COPY --chown=node starship.toml /home/node/.config/starship.toml
