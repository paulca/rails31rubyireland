!SLIDE bullets
# Have it your way #

* Sensible defaults
* One Line Gemfile swaps

!SLIDE

# Default Gemfile #

    @@@ruby
    # Gemfile
    group :assets do
      gem 'sass-rails', "  ~> 3.1.0.rc"
      gem 'coffee-rails', "~> 3.1.0.rc"
      gem 'uglifier'
    end

    gem 'jquery-rails'

!SLIDE

# Bam! #

    @@@ruby
    # Gemfile
    group :assets do
      gem 'uglifier'
    end

    gem 'prototype-rails'