require 'rake/testtask'
require 'find'

desc 'say hello'
task :hello do
  puts 'hello there'
end

desc 'run rests'
task :default => :test

Rake::TestTask.new(:test) do |t|
  t.libs << 'test'
  t.libs << 'lib'
  t.test_files = FileList['test/**/*_test.rb']
end

desc 'list all files'
task :list do
  Find.find('../todolist_project') do |path|
    if FileTest.directory?(path)
      if File.basename(path)[0] == ?.
        Find.prune
      else
        next
      end
    else
      puts path
    end
  end
end
