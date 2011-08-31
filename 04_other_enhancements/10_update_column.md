!SLIDE bullets
# update_column #

* skips validations

!SLIDE

    @@@ruby
    User.first.update_column(:name, "paul")
    # => true