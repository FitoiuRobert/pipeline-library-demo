@Library('pipeline-library-demo')_
import com.cleverbuilder.*
def gitDir = "$JENKINS_HOME/workspace/git"

pipeline{
    agent none
    stages{
        stage('Stage One'){
        
            steps{

                    echo "   "
                    script{
                                def var123 = GlobalVars.foo
                                println var123
                                def process = new ProcessBuilder([ "/bin/bash", "-c", "touch " + "\""+ STAGE_NAME+ "\""])
                                    .directory(new File(gitDir))
                                    .redirectErrorStream(true) 
                                    .start()
                                      process.outputStream.close()
                                      process.inputStream.eachLine {println it}
                                      process.waitFor();
                                    println process.exitValue()
                       
                       /*
                        println cmd
                        def sout = new StringBuffer(), serr = new StringBuffer()
                        def proc = 'ls ${env.JENKINS_HOME}'.execute()

                        proc.consumeProcessOutput(sout, serr)
                        proc.waitForOrKill(1000)
                        println sout
                        */
                    }
                    
            }
        }
        stage('Stage Two'){
            steps{
                echo "   "
            }
        }
    }
}
