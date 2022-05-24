node {
    stage('Git checkout') {
        git branch: "${params.BRANCH}", url: 'https://github.com/Projet-Automation-Infra-SI-Ynov/Images'
    }
    stage('Add Registry address IP to inventory file') {
        sh "sed -i 's/IP_REGISTRY/${params.REGISTRY_IP}/g' ./Grafana/grafana.ini"
    }
    stage('Add Registry address IP to playbook file') {
        sh "sed -i 's/IP_REGISTRY/${params.REGISTRY_IP}/g' ./Grafana/grafana.yml"
    }
    stage('Execute playbook') {
        sh "ansible-playbook -i ./Grafana/grafana.ini ./Grafana/grafana.yml"
    }
}