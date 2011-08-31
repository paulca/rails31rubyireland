!SLIDE smaller
# http_basic_authenticate_with #

    @@@ruby
    class PostsController < ApplicationController
      http_basic_authenticate_with :name => "dhh",
                                   :password => "secret",
                                   :except => :index

      def index
        render :text => "Everyone can see me!"
      end

      def edit
        render :text => "You need the password"
      end
    end