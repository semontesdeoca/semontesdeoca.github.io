Guide to move Blogger to Github Pages

1.	Create blog repository in GitHub following these instructions and try it out
2.	Delete the index.html file from your repository as it will be replaced by Jekyll
3.	Download Ruby 2.2.X on your computer (windows 32bit -> https://rubyinstaller.org/downloads/)
4.  When installing Ruby, make sure you add Ruby executables to your PATH
4.	Go to: Start->Ruby->Start Command Prompt with Ruby and enter “gem install bundler”
5.	Once the bundler is installed, enter “gem install jekyll”
5.	Once Jekyll is installed, enter “bundle install”
6.	Once Jekyll is installed, navigate to the folder were your repository is stored by entering “cd yourdirectory” (replace yourdirectory with your repository directory e.g. “C:\Users\username\Documents\blog”)
7.	Now that the command prompt is in the right directory, enter “Jekyll new yourname.github.io” (replace yourname with your github username)
8.	Commit your changes to github and check what has changed under yourname.github.io
9.	Create blog repository in GitHub
