require "rubygems"
require "bundler/setup"

begin
  Bundler.setup(:default, :ci)
rescue Exception => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end

require 'rake'

require 'jeweler'
Jeweler::Tasks.new do |gem|
  gem.name = "mush"
  gem.summary = "A Ruby replacement for bash+ssh."
	gem.description = "A Ruby replacement for bash+ssh, providing both an interactive shell and a library.  Manage both local and remote unix systems from a single client."
  gem.email = "mjording@opengotham.com"
  gem.homepage = "http://rush.heroku.com/"
	gem.has_rdoc = true
	gem.add_development_dependency "rspec"
  gem.add_development_dependency "yard"
  gem.add_dependency "thin"
 	gem.add_dependency "session"
	gem.files = FileList["[A-Z]*", "{bin,lib,spec}/**/*"]
  gem.authors = ["adamwiggins","mjording"]
  gem.executables = %w(rush rushd)
  gem.default_executable = "rush"
  # gem is a Gem::Specification... see http://www.rubygems.org/read/chapter/20 for additional settings
end
Jeweler::RubygemsDotOrgTasks.new

require 'rspec'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = FileList['spec/**/*_spec.rb']
end

RSpec::Core::RakeTask.new(:rcov) do |spec|
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :default => :spec

require 'yard'
YARD::Rake::YardocTask.new


######################################################
