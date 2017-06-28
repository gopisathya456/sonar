Installation of Sonar 5.6.6
Download sonarqube
> cd sonarqube-5.6.6/bin/macosx-universal-64

start sonar
> ./sonar.sh console


Installing sonar scanner

1. Download sonar scanner sonar-scanner-3.0.3.778-macosx

2. Add the following in ~/.bash_profile

export SONAR_RUNNER_HOME="/Users/gopi/Downloads/sonar-scanner-3.0.3.778-macosx"
export PATH="/Users/gopi/Downloads/sonar-scanner-3.0.3.778-macosx/bin:$PATH"

3. refresh bash profile
> source ~/.bash_profile

Running sonar scanner

go to your projects foldr

1. Create a file sonar-project.properties with following contents

# This file is used by sonar-runner
# 
# Required metadata
sonar.projectKey=myproject
sonar.projectName=custom modules only, features excluded
sonar.projectVersion=1.0

# Comma-separated paths to directories with sources (required)
sonar.sources=.
sonar.exclusions=jquery*,noteresource/**
sonar.

# Language
sonar.language=php

# To deactivate features related to unit tests execution and coverage
sonar.dynamicAnalysis=false

# Encoding of the source files
sonar.sourceEncoding=UTF-8

sonar.phpCodesniffer.argumentLine=--ignore=jquery,custom_features
sonar.php.file.suffixes=php,module,inc,install,test,profile,theme,css,js,txt,info

2. In the command line run following
> sonar-scanner
