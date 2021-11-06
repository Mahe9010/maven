pipeline{
         agent any
	 environment {
             PATH = "/opt/apache-maven-3.8.3/bin:$PATH"
         }
         stages
            {
               stage('Git')
                 {
                   steps{
                         echo "Building the code.........."
                         git branch: 'main', url: 'https://github.com/Garlapatisranga/Maven-Project-1.git'
                        }
                  }
             
               stage('Clean')
                 {
                  steps{
                       echo "Cleaning the code.........."
                       sh "mvn clean"
                        }
                  }
               stage('Test')
                  {
                   steps{
                        echo"Testing the code....."
                        sh "mvn test"
                        }
                  }
              stage('install')
                  {
                   steps{
                        echo "Creating a War file for the Project........"
                        sh "mvn install"
                        }
                  }
             stage('Permissions')
                  {
                  steps{
                       echo "Copying to tomcat...."
		       sh "chmod 777 build.sh"
		       }
                  }
		  stage('Deploy')
                  {
                  steps{
                       echo "Copying to tomcat...."
		       sh "./build.sh"
		       }
        }
     }
  } 
