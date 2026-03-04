require "rake/testtask"
require 'find'

desc 'Say hello'
task :hello do
  puts "Hello there. This is the 'hello' task."
end

desc 'Run tests'
task :default => :test #

Rake::TestTask.new(:test) do |t| # TestTask is a class
  # t represents the task object and block is where we customize how the task behaves
  t.libs << "test" # tells Rake to add test and lib to the $LOAD_PATH
  t.libs << "lib"
  t.test_files = FileList['test/**/*_test.rb']   # tells the test task while files to run as tests

  # start in the test directory
  # ** include all subdirectories (recursively)
  # *_test.rb any file whose name ends in _test.rb
end

desc 'List all public files'
task :list_public do
  Find.find(".") do |path|
    Find.prune if File.basename(path).start_with?('.')
    puts path
  end
end


# running the rake command means you're running the executable that comes from the rake gem and one of the first things it does is look for a Rakefile
# it then loads that file
# and based on the command Rake runs the appropriate task(s) it just defined
