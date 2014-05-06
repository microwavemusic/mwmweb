desc "Build Middleman project"
task :generate do
  puts "## Building static site in ./build"
  system "middleman build --clean"
  cd "build" do
    system "git init"
    system "git remote add origin "
  end
end

desc "Push the build to GitHub"
task :push do
  puts "## Deploying build to GitHub"
  cd "build" do
    system "git add -u ."
    system "git commit -m \"Site updated at #{Time.now.utc}\""
    system "git push origin master --force"
  end
end

desc "Build Middleman project and deploy to GitHub"
task :deploy => [:generate, :push] do
end
