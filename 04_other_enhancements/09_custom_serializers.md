!SLIDE
# Custom Serializers #

    @@@ruby
    class User < ActiveRecord::Base
      serialize :bank_account_number
    end
    
!SLIDE smaller

    @@@ruby
    class User < ActiveRecord::Base
      class Base64
        def load(text)
          return unless text
          text.unpack('m').first
        end

        def dump(text)
          [text].pack 'm'
        end
      end

      serialize :bank_account_number, Base64.new
    end

<span class="cf">[http://edgerails.info/articles/what-s-new-in-edge-rails/2011/03/09/custom-activerecord-attribute-serialization/index.html](http://edgerails.info/articles/what-s-new-in-edge-rails/2011/03/09/custom-activerecord-attribute-serialization/index.html)</span>