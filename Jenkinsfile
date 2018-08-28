node{
        checkout scm 
        stage('Build curator'){
                sh "wget https://github.com/elastic/curator/archive/v5.5.4.tar.gz"
                sh "tar zxf v5.5.4.tar.gz"
                sh "cd curator-5.5.4"
                sh "pip install virtualenv"
                sh "~/.local/bin/virtualenv venv"
                sh ". venv/bin/activate"
                sh "pip install -r requirements.txt"
        }   
        stage('Run Curator'){
                sh "./run_curator.py --dry-run examples/actions/delete_indices.yml --config examples/curator.yml"
        }   
}
