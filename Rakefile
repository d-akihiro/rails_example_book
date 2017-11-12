namespace :book do
  task :resource_copy do
    Dir.mkdir 'images' unless Dir.exists? 'images'
    Dir.glob("book/*/images/*").each do |image|
      FileUtils.copy(image, "images/" + File.basename(image))
    end
  end

  desc "build book"
  task :build => :resource_copy do
    `bundle exec asciidoctor-pdf -r asciidoctor-pdf-cjk rails_example.adoc 2>/dev/null`
  end
end
