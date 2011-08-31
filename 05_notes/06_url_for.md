!SLIDE small

# url_for and named url helpers #
## now accept :subdomain and :domain as options ##

    @@@ruby
    <%= posts_url(:subdomain => 'rails', 
                  :domain => 'rubyireland.com') %>
    # => http://rails.rubyireland.com/posts