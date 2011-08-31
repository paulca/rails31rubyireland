!SLIDE 
# Asset Pipeline #

<span class="cf">http://railscasts.com/episodes/279-understanding-the-asset-pipeline</span>

!SLIDE bullets

# Why's it cool? #

* Asset packaging is a pain
* Speed
* It Just Works
* Assets have a home

!SLIDE

# app/assets/images #
# app/assets/javascripts #
# app/assets/images #

!SLIDE 

# app/assets/images/logo.png #
# yourapp.dev/assets/logo.png #

!SLIDE commandline

    rake assets:precompile

!SLIDE smaller

    @@@ css
    # app/assets/stylesheets/home.css.scss.erb
    background-image: url(<%= asset_path('logo.png') %>)
    # => /assets/logo-d2abf5298e15404b164c7125f527dd99.png