template = '''
apiVersion: v1
kind: Pod
metadata:
  labels:
    run: kubernetes
  name: kubernetes
spec:
  serviceAccountName: kubernetes
  containers:
  - image: kaizenacademy/my-binary:1.0.0
    name: kubernetes
    '''

podTemplate(cloud: 'kubernetes', label: 'kubernetes', name: 'kubernetes', yaml: template) {
    node("kubernetes") {
        container("kubernetes") {
    stage("Checkout SCM") {
        git branch: 'main', url: 'https://github.com/issallina/may-group-2026-cd.git'
    }
    
    stage("Deploy") {
        sh "helm upgrade --install flask ./flask-app --set deployment.image=isalina1318/jenkins-flask-app"
    }

}
}
}
