# -*- ruby -*-

require 'rubygems'
require 'hoe'
gem 'rake-compiler', '>= 0.4.1'
require "rake/extensiontask"

Hoe.spec 'usb' do
  developer 'Tanaka Akira', 'akr@fsij.org'

  self.history_file      = 'ChangeLog'
  self.readme_file       = 'README'
  self.testlib           = :minitest

  extra_dev_deps << ['rake-compiler', '>= 0.4.1']

  self.spec_extras = {
    :extensions            => ["ext/usb/extconf.rb"],
  }

  Rake::ExtensionTask.new "usb", spec do |ext|
    ext.lib_dir = File.join(*['lib', ENV['FAT_DIR']].compact)
  end
end

task :test => :compile
