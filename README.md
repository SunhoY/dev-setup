#dev-setup

1. Install Git

sudo apt-get install git

2. Install Java(Oracle 8)

sudo apt-get install python-software-properties
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update

sudo apt-get install oracle-java8-installer

sudo update-alternatives --config java

sudo nano /etc/environment

JAVA_HOME="YOUR_PATH"

source /etc/environment

echo $JAVA_HOME

3. Install Ruby with rbenv(ruby version manager)

git clone https://github.com/sstephenson/rbenv.git ~/.rbenv

echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc
type rbenv

3.1 install ruby-build

git clone https://github.com/sstephenson/ruby-build.git ~/.rbenv/plugins/ruby-build

3.2 install ruby 2.2.3

rbenv install 2.2.3

if requires dependencies

try sudo apt-get install -y libssl-dev libreadline-dev zlib1g-dev
and try again

4. install rails

to install rails, have to install nodejs first

sudo apt-get install nodejs

gem install rails -v 4.2.4

rbenv global 2.2.3

5. Install Android Studio

download from http://developer.android.com/intl/ko/sdk/index.html#top

sudo unzip android-studio-ide-141.2288178-linux.zip -d /opt

run /opt/android-studio/bin/studio.sh

if it show unable to run mksdcard SDK tool

sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6

try again

vim /usr/share/applications/android-studio.desktop

[Desktop Entry]
Version=1.0
Type=Application
Name=Android Studio
Icon=/opt/android-studio/bin/studio.ico
Exec="/opt/android-studio/bin/studio.sh" %f
Comment=Develop with pleasure!
Categories=Development;IDE;
Terminal=false

6. Install Rubymine

download from https://www.jetbrains.com/ruby/download/

cd /opt
tar -zxvf Ruby

7. Install Postgresql

if didn't install 3rd party applications on os installation

Create the file /etc/apt/sources.list.d/pgdg.list, and add a line for the repository

add the following line

deb http://apt.postgresql.org/pub/repos/apt/ trusty-pgdg main

run below command

wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | \
  sudo apt-key add -
sudo apt-get update
sudo apt-get install libpq-dev
sudo apt-get install postgresql-contrib

install pg gem

gem install pg

error might be occured if libpq-dev has not installed


8. Create Rails project

gem install rails

rails new {project}

if error occurs with sqlite3

try
sudo apt-get install ruby-dev
sudo apt-get install sqlite3 libsqlite3-dev

and bundle again

if don't want to see the error with sqlite

rails new {project} --database=postgresql

9. Rspec setup



