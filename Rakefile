
desc 'Remove the dist directory'
task :clean do
  rm_r 'dist'
end

desc 'Assemble files for distribution'
task :package => [:clean] do
  mkpath 'dist'
  readme = IO.read('README')
  readme = "/*\n" + readme.split("\n").map { |line| " * #{line}" }.join("\n") + "\n *\n */\n\n"
  statusjs = IO.read('src/javascripts/status.js')
  open('dist/status.js', 'w') do |f|
    f.write(readme + statusjs)
  end
  cp_r 'src/images', 'dist'
end