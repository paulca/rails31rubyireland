!SLIDE
# has_secure_password #
    @@@ruby
    class User < ActiveRecord::Base
      has_secure_password
    end

!SLIDE smaller

    @@@ruby
    user = User.new(:name => "david",
                    :password => "",
                    :password_confirmation => "nomatch")
    user.save
    # => false, password required
    user.password = "mUc3m00RsqyRe"
    user.save
    # => false, confirmation doesn't match
    user.password_confirmation = "mUc3m00RsqyRe"
    user.save 
    # => true
    user.authenticate("notright")                                  
    # => false
    user.authenticate("mUc3m00RsqyRe")                             
    # => user
    User.find_by_name("david").try(:authenticate, "notright")      
    # => nil
    User.find_by_name("david").try(:authenticate, "mUc3m00RsqyRe") 
    # => user

<span class="cf">[https://gist.github.com/958283](https://gist.github.com/958283)</span>