require 'rubygems'
require 'rake'
require 'uuid'
task :default => :post

desc 'Create new post with rake "post[post-name]"'
task :post, [:title,:tag] do |t, args|
  args.with_defaults(:tag => 'other')
  if args.title then
    new_post(args.title,args.tag)
  else
    puts 'rake "post[post-name]"'
  end
end



def new_post(title,tag)
  time = Time.now
  filename = "_posts/" + time.strftime("%Y-%m-%d-") + title + '.md'
  if File.exists? filename then
    puts "Post already exists: #{filename}"
    return
  end
  uuidObj = UUID.new
  uuid = uuidObj.generate
  File.open(filename, "wb") do |f|
    f << <<-EOS
---
title: #{title}
layout: post
guid: urn:uuid:#{uuid}
tags:
  - #{tag}
---


EOS
  end
  puts "created #{filename}"

end
