!SLIDE
# Identity Map #

    @@@ruby
    post = Post.find(1)
    other_post = Post.find(1)
    post.id == other_post.id
    # => true
    
    post.object_id == other_post.object_id
    # => true

<span class="cf">[https://github.com/rails/rails/blob/master/activerecord/lib/active_record/identity_map.rb](https://github.com/rails/rails/blob/master/activerecord/lib/active_record/identity_map.rb)</span>