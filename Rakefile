require 'active_record'
require 'yaml'


desc "Migrate the database through scripts in db/migrate. Target specific version with VERSION=x"  
task :create_tables => :environment do  
  ActiveRecord::Migrator.migrate('db/tables', ENV["VERSION"] ? ENV["VERSION"].to_i : nil )  
end 

task :environment do
    ActiveRecord::Base.establish_connection(YAML::load(File.open('db/database.yml')))  
    ActiveRecord::Base.logger = Logger.new $stderr
end
