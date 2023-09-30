echo "Using SHELL $SHELL"

# Adding showFiles\hidefiles as a command to show/hide files from Finder
alias showFiles='defaults write com.apple.finder AppleShowAllFiles YES; killall Finder /System/Library/CoreServices/Finder.app'
alias hideFiles='defaults write com.apple.finder AppleShowAllFiles NO; killall Finder /System/Library/CoreServices/Finder.app'

# Enable colors in bash
export CLICOLOR=1
# Ubuntu color theme
# export LSCOLORS=GxBxCxDxexegedabagaced
# get current git branch
parse_git_branch() {
  git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'
}
# username@hostname:pwd (git branch) $
# export PS1="\e[0;35m->> \e[1;34m\W\e[0;32m\$(parse_git_branch)\e[0;37m $ "
# export PS1="\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[0;32m\]\$(parse_git_branch)\[\033[00m\]\$ "
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\e[1;34m\w\e[0;32m\$(parse_git_branch)\e[0;37m $ "
# export PS1="\u@\h $ "
# Dark color theme
# export LSCOLORS=GxFxCxDxBxegedabagaced
# Light color theme
# export LSCOLORS=ExFxBxDxCxegedabagacad
# Ubuntu color theme
# export PS1="\e[0;35m->> \e[1;34m\W\e[0;32m\$(parse_git_branch)\e[0;37m $ "

### Shortcut for ls
alias ls='ls -aG'
# -G colorizes output
# -h makes sizes human readable
# -a show hidden . files
# -F adds the following
#  	/ for directory
#  	* for executable
#  	@ for symbolic link (or that the file has extended attributes).
#  	= for socket
#  	% for whiteout
#  	| for named pipe (FIFO)
#  	> for door

# Adding brew/homebrew before default
# export PATH="/usr/local/bin:/usr/local/sbin:$PATH"

# Setting up jenv/Java/java path/ 
export PATH="$HOME/.jenv/bin:$PATH"
eval "$(jenv init -)"
jenv enable-plugin maven
jenv enable-plugin export
# ^The eval command will unset the JAVA_HOME

# Setting up Android
export ANDROID_HOME="${HOME}/Library/Android/sdk"
export ANDROID_SDK="${ANDROID_HOME}"
export ANDROID_SDK_HOME="${ANDROID_HOME}"
export ANDROID_SDK_ROOT="${ANDROID_HOME}"
export PATH="${PATH}":"${ANDROID_HOME}/tools":"${ANDROID_HOME}/platform-tools":"${ANDROID_HOME}/tools/bin"
export PATH="${PATH}":"${ANDROID_HOME}/build-tools/$(/bin/ls -1r $ANDROID_HOME/build-tools | head -1)"
# jenv add "/Applications/Android Studio.app/Contents/jre/jdk/Contents/Home" 

# Setting Maven
#MAVEN_HOME
# export M2_HOME="/usr/local/opt/maven/libexec"
# export M2_HOME="/usr/local/Cellar/maven/<3.5.2>/libexec"
# export M2=$M2_HOME/bin
# export PATH=$PATH:$M2_HOME/bin

# Setting Gradle
# gradle home = /usr/local/opt/gradle/libexec
# gradle home = /usr/local/Cellar/gradle/<4.6>/libexec
# export GRADLE_USER_HOME=~/.gradle

# Setting Groovy
# export GROOVY_HOME="/usr/local/opt/groovy/libexec"

# Setting Grails
# GRAILS_HOME=/usr/local/opt/grails/libexec

# Setting GO
export PATH="/usr/local/opt/go/libexec/bin:$PATH"

# setting gnu sed from brew as default
export PATH="/usr/local/opt/gnu-sed/libexec/gnubin:$PATH"

# setting gnu awk from brew as default
export PATH="/usr/local/opt/gawk/libexec/gnubin:$PATH"

# setting curl from brew as default
export PATH="/usr/local/opt/curl/bin:$PATH"

# setting vim from brew as default
export PATH="/usr/local/opt/vim/bin:$PATH"

# Adding local bin to path
export PATH="${PATH}":"$HOME/bin"

# Homeassistant
# source $HOME/Documents/homeassistant/bin/activate

## SETTING tomcat
# export TOMCAT_HOME="/usr/local/opt/tomcat"
# export CATALINA_HOME=“/usr/local/opt/tomcat/libexec”
# /usr/local/opt/tomcat/libexec
# CATALINA_OPTS="$CATALINA_OPTS -server -Xms1024m -Xmx3072m"

# Setting up softwares installed through brew
# Setting up node and npm
# export PATH="$PATH:/usr/local/share/npm/bin"
# export PATH="/usr/local/opt/gettext/bin:$PATH"
# export PATH="/usr/local/opt/libxml2/bin:$PATH"

## sqlite
# export PATH="/usr/local/opt/sqlite/bin:$PATH"

## SETTING SDKMAN
# export SDKMAN_DIR="$HOME/.sdkman"
# [[ -s "$HOME/.sdkman/bin/sdkman-init.sh" ]] && source "$HOME/.sdkman/bin/sdkman-init.sh"

## Setting pyenv
# if command -v pyenv 1>/dev/null 2>&1; then
#   eval "$(pyenv init -)"
# fi
