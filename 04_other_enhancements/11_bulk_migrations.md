!SLIDE

# Bulk migrations #
    
    @@@ruby
    change_table(:users, :bulk => true) do |t|
      t.string :company_name
      t.change :birthdate, :datetime
    end