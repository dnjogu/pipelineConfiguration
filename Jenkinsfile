#!/usr/bin/env groovy
pipeline {
    agent { node { label 'master' } }



    parameters {
    	string(defaultValue: '', description: '', name: 'BRANCH_NAME' ) 
    	choice (choices: 'DEBUG\nRELEASE\nTEST') 
      	}

      	stages {
      	 stage ( 'process' ) 
      	 { 
      	 	when 
      	 		{ allOf 
      	 			{ expression { params . BRANCH_NAME == "master" } 
      	 			  expression { params . BUILD_TYPE == 'RELEASE' } 
      	 						} 
  	 						} 
  	 						steps 
  	 						{ echo "Kicking off production build\n" } 
  	 						} 
 						} 
					} 
