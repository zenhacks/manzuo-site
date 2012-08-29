SSH_USER = 'yangchenun'
SSH_HOST = 'maxwell'
SSH_DIR  = '/srv/www/htdocs/easymoo_index/'

desc "Build the website from source"
task :build do
  puts "## Building website"
  status = system("bundle exec middleman build --clean")
  puts status ? "OK" : "FAILED"
end

desc "Deploy website via rsync"
task :deploy do
  puts "## Deploying website via rsync to #{SSH_HOST}"
  status = system("rsync -cuavz build/* #{SSH_HOST}:#{SSH_DIR}")
  puts status ? "OK" : "FAILED"
end

desc "Build and deploy website"
task :build_deploy => [:build, :deploy] do
end
