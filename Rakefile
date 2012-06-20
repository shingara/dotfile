namespace :zsh do
  desc "Install zsh"
  task :install do
    zsh_dir = File.join(ENV['HOME'], '.oh-my-zsh')
    if Dir.exists?(zsh_dir)
      system "cd #{zsh_dir} && git pull"
    else
      system "git clone git://github.com/robbyrussell/oh-my-zsh.git #{zsh_dir}"
    end
    system "rm ~/.zshrc"
    system "ln -s ~/dotfile/.zshrc ~/.zshrc"
    unless ENV['SHELL'] =~ /zsh/
      system "chsh -s /bin/zsh"
    end
  end
end

namespace :git do
  desc "install gitconfig"
  task :install do
    system "rm ~/.gitconfig"
    system "ln -s ~/dotfile/gitconfig ~/.gitconfig"
  end
end

desc 'install all dotfile'
task :install => ['git:install', 'zsh:install']
