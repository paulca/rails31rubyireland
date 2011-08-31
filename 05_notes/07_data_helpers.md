!SLIDE small

# html5 data attributes #

    @@@ruby
    <%= link_to "Posts", [:posts],
                         {:data => {:context => 'index'}} %>
    # => <a href="/posts" data-context="index">Posts</a>