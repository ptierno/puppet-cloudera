require 'rubygems'
require 'puppetlabs_spec_helper/rake_tasks'

desc "Run visual spec tests on an existing fixtures directory"
RSpec::Core::RakeTask.new(:spec_standalonev) do |t|
  t.rspec_opts = ['--color', '--format documentation']
  t.pattern = 'spec/{classes,defines,unit}/**/*_spec.rb'
end

# https://github.com/stahnma/puppet-modules/blob/master/common/Rakefile
desc "Run puppet in noop mode and check for syntax errors."
task :validate do
  Dir['manifests/**/*.pp'].each do |path|
    sh "puppet parser validate --noop #{path}"
  end
end
