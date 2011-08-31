!SLIDE
# belongs_to on command line #

## rails g model post user:belongs_to ##

    @@@ruby
    class CreatePosts < ActiveRecord::Migration
      def change
        create_table :posts do |t|
          t.belongs_to :user

          t.timestamps
        end
        add_index :posts, :user_id
      end
    end
    