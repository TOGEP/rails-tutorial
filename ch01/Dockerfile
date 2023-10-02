FROM ruby:3.2-slim

# Install packages
RUN apt-get update && apt-get install -y \
  build-essential \
  libpq-dev \
  nodejs \
  git

# Install gems
RUN mkdir /app
WORKDIR /app
ADD Gemfile /app/Gemfile
RUN bundle install

# Add app
ADD . /app

# Start server
CMD ["rails", "server", "-b", "0.0.0.0"]
