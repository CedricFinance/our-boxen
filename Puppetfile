# This file manages Puppet module dependencies.
#
# It works a lot like Bundler. We provide some core modules by
# default. This ensures at least the ability to construct a basic
# environment.

# Shortcut for a module from GitHub's boxen organization
def github(name, *args)
  options ||= if args.last.is_a? Hash
    args.last
  else
    {}
  end

  if path = options.delete(:path)
    mod name, :path => path
  else
    version = args.first
    options[:repo] ||= "boxen/puppet-#{name}"
    mod name, version, :github_tarball => options[:repo]
  end
end

# Shortcut for a module under development
def dev(name, *args)
  mod name, :path => "#{ENV['HOME']}/src/boxen/puppet-#{name}"
end

def githubsource(name, options=nil)
  options ||= {}
  options[:repo] ||= "boxen/puppet-#{name}"
  mod name, :git => "git://github.com/#{options[:repo]}.git"
end

# Includes many of our custom types and providers, as well as global
# config. Required.

github "boxen", "3.3.8"

# Core modules for a basic development environment. You can replace
# some/most of these if you want, but it's not recommended.

github "dnsmasq",     "1.0.1"
github "foreman",     "1.1.0"
github "gcc",         "2.0.1"
github "git",         "1.3.7"
github "go",          "2.0.1"
github "homebrew",    "1.6.0"
github "hub",         "1.3.0"
github "inifile",     "1.0.1", :repo => "puppetlabs/puppetlabs-inifile"
github "module-data", "0.0.1", :repo => "ripienaar/puppet-module-data"
github "nginx",       "1.4.3"
github "nodejs",      "3.5.0"
github "openssl",     "1.0.0"
github "phantomjs",   "2.1.0"
github "pkgconfig",   "1.0.0"
github "repository",  "2.3.0"
github "ruby",        "7.1.6"
github "stdlib",      "4.1.0", :repo => "puppetlabs/puppetlabs-stdlib"
github "sudo",        "1.0.0"
github "xquartz",     "1.1.1"
github "tmux",       "1.0.2"

# Optional/custom modules. There are tons available at
# https://github.com/boxen.

githubsource "alfred"
github "graphviz",    "1.0.0"
github "pkgconfig",   "1.0.0"
github "swig",        "1.0.0"
github "pcre",        "1.0.0"
github "googledrive", "1.0.1"
github "postgresql",  "2.0.1"
github "sysctl",      "1.0.0"
github "sourcetree",  "1.0.0"
github "bash",        "1.1.0"
github "osx",         "2.2.0"
github "atlassian_sdk", "1.0.2", :repo => "CedricFinance/puppet-atlassian_sdk"
github "tig", "1.0.0", :repo => "skottler/puppet-tig"

