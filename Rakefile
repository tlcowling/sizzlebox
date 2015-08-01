task :install do
  system 'librarian-puppet install'
end

task :gencert do
  system './sslbox'  
end

task :start do
  system 'vagrant up'
end

desc "install puppet modules, generate certificates, start vagrant"
task :default => [:install, :gencert, :start]
