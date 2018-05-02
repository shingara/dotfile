current_dir = File.dirname(__FILE__)
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
    system "ln -s #{File.join(current_dir, 'zshrc')} ~/.zshrc"
    unless ENV['SHELL'] =~ /zsh/
      system "chsh -s /bin/zsh"
    end
  end
end

namespace :git do
  desc "install gitconfig"
  task :install do
    system "rm ~/.gitconfig"
    system "ln -s #{File.join(current_dir, 'gitconfig')} ~/.gitconfig"
  end
end

namespace :tmux do
  desc "install tmux.conf"
  task :install do
    system "rm ~/.tmux.conf"
    system "ln -s #{File.join(current_dir, 'tmux.conf')} ~/.tmux.conf"
  end
end


desc 'install all dotfile'
task :install => ['git:install', 'zsh:install']
