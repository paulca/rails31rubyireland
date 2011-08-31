!SLIDE
# Force SSL #

    @@@ruby
    # config/application.rb
    module MyApp
      class Application < Rails::Application
        config.force_ssl = true
      end
    end

!SLIDE small
# Force SSL in controller #

    @@@ruby
    # app/controllers/posts_controller.rb
    class PostsController < ActionController::Base
      force_ssl :only => :create
    end
    
<span class="cf">[http://www.simonecarletti.com/blog/2011/05/configuring-rails-3-https-ssl/](http://www.simonecarletti.com/blog/2011/05/configuring-rails-3-https-ssl/)</span>