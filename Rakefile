#!/usr/bin/env rake

require 'bundler/setup'
require 'thor'

$LOAD_PATH.unshift 'lib'

task :default do
  $LOAD_PATH.unshift 'test'
  Dir['test/**/*_test.rb'].map(&File.method(:expand_path)).each(&method(:require))
end

namespace :assets do
  desc 'Compile all assets'
  task :precompile do
    load 'tasks/assets.thor'
    AssetsCLI.new.compile
  end
end

namespace :docs do
  desc 'Compile all assets'
  task :download_all do
    load 'tasks/docs.thor'
    DocsCLI.new.download(:all)
  end
end
