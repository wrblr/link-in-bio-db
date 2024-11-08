# link-in-bio-db
# template for updating db items in future:
desc "Fill the database tables with some sample data"
task({ :sample_data => :environment }) do
  puts "Creating sample data..."

  if Rails.env.development?
    puts "Deleting the previous data..."
    Item.destroy_all
  end

  puts "Creating first item..."
  item_1 = Item.new
  item_1.link_url = "https://paulgraham.com/startupideas.html"
  item_1.link_description = "How to Get Startup Ideas"
  item_1.thumbnail_url = "https://fastly.picsum.photos/id/554/200/200.jpg?hmac=wvBDWVN6iXLUYv4DYpQ9fWSg_2y3dCYyzy4N_6H26pY"
  item_1.save

  puts "Creating second item..."
  item_2 = Item.new
  item_2.link_url = "..."
  # ... etc.
  puts "Done!"
end
