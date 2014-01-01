# Original idea by MattHall
# https://gist.github.com/MattHall/1801090
# usage rake new_post title="my awesome title"

require 'date'

task :new_post do
  title = ENV['title']
  path = "_posts/#{Date.today}-#{title.downcase.gsub(/[^[:alnum:]]+/, '-')}.md"
  if File.exist?(path)
    puts "[WARN] File exists - skipping create"
  else
    File.open(path, 'w') do |file|
      file.puts '---'
      file.puts 'layout: default'
      file.puts 'title: ' + title.capitalize
      file.puts '---'
      file.puts "\n\n"
      file.puts '{{ page.date | date: "%d %B %Y" }}'
      file.puts "\n"
      file.puts "[link to this post]({% post_url #{Date.today}-#{title.downcase.gsub(/[^[:alnum:]]+/, '-')} %})"
    end
  end
end