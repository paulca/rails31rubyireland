!SLIDE bullets incremental
# What about Rails 3.0? #

* bundler by default
* ARel
* Routing
* Modular Architecture
* Active Model
* Action Mailer
* Default XSS Protection

!SLIDE
# bundler by default #

# Gemfile #

    @@@ruby
    source 'http://rubygems.org'
    gem 'rails', '3.1.0'
    

    bundle install

!SLIDE
# Arel #

    @@@ruby
    class Post
      scope :published, where(:published => 1)
    end
    
    Post.published.where(:title => "Rails 3.1")
    # SELECT * FROM posts
    # where published = 1
    # and title = 'Rails 3.1'

!SLIDE

# New Router #
    @@@ruby
    # routes.rb
    MyApp::Application.routes.draw do
      resources :post do
        member { get :delete }
      end
      match "/signin", :to => "sessions#new"
    end

!SLIDE small

# Modular Architecture #

    @@@ruby
    nil.blank?
    # NoMethodError: undefined method
    # `blank?' for nil:NilClass

    require 'active_support'
    require 'active_support/core_ext/object/blank'
    nil.blank?
    # => true

<span class="cf">cf. [http://edgeguides.rubyonrails.org/active_support_core_extensions.html](http://edgeguides.rubyonrails.org/active_support_core_extensions.html)</span>

!SLIDE smaller

# Active Model #

    @@@ruby
    require 'active_model'

    class Person
      include ActiveModel::Validations

      validates_presence_of :first_name, :last_name

      attr_accessor :first_name, :last_name
      def initialize(first_name, last_name)
        @first_name, @last_name = first_name, last_name
      end
    end

    a = Person.new("Fred", nil)
    a.valid? # => false
    a.last_name = "Flintstone"
    a.valid? # => true

<span class="cf">cf. [http://www.rubyinside.com/rails-3-0s-activemodel-how-to-give-ruby-classes-some-activerecord-magic-2937.html](http://www.rubyinside.com/rails-3-0s-activemodel-how-to-give-ruby-classes-some-activerecord-magic-2937.html)</span>

!SLIDE smaller

# ActionMailer #

    @@@ruby
    # app/mailers/user_mailer.rb
    class UserMailer < ActionMailer::Base
      default :from => "notifications@example.com"

      def welcome_email(user)
        @user = user
        @url  = "http://example.com/login"
        mail :to => user.email,
             :subject => "Welcome to My Awesome Site"
      end
    end

<span class="cf">cf. [http://edgeguides.rubyonrails.org/action_mailer_basics.html](http://edgeguides.rubyonrails.org/action_mailer_basics.html)</span>

!SLIDE smaller

# Default XSS Protection #

    @@@ruby
    # app/views/something/something.html.erb
    <%= "We &gt; I" %>
    # => "We &gt; I"
    
    <%= raw "We &gt; I" %>
    # => "We > I"

<span class="cf">cf. [http://guides.rubyonrails.org/security.html](http://guides.rubyonrails.org/security.html)</span>