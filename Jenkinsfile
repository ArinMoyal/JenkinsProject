pipeline {
  agent { node { label 'slave01' } }

   stages {
     stage "C"
       if ({$LANGUAGE} in ["C","all"]) {
        echo "C selected"
    }

     stage "Python"
       if ({$LANGUAGE} in ["Python","all"]) {
        echo "Python selected"
    }

     stage "Bash"
       if ({$LANGUAGE} in ["Bash","all"]) {
        echo "Bash selected"
    }

   }
}
