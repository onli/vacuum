require 'bundler'
require 'rspec/core/rake_task'

Bundler::GemHelper.install_tasks

desc 'Run all specs in spec directory'
RSpec::Core::RakeTask.new(:spec) do |t|
  t.pattern    = 'spec/**/*_spec.rb'
  opts = []
  opts << '--tag ~@synchrony' if RUBY_VERSION < '1.9'
  opts << '--tag ~@jruby'     if RUBY_PLATFORM == 'java'
  t.rspec_opts = opts.join(' ') unless opts.empty?
end

task :default => [:spec]
