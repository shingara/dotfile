namespace :zsh do
  desc "Install zsh"
  task :install do
    system "git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh"
    system "ln -s ~/dotfile/.zshrc ~/.zshrc"
    system "chsh -s /bin/zsh"
  end
end
