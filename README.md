# inascode
deploy-puma-server
gcloud compute instances create --boot-disk-size=10GB --image=ubuntu-1604-xenial-v20170815a --image-project=ubuntu-os-cloud --machine-type=g1-small --tags puma-server --restart-on-failure --metadata startup-script-url=https://gist.githubusercontent.com/Nonamed123/1e8afd0c2abab59994493d5e4506ee94/raw/00835e49064eb586dc251679bb592893247f3c44/Script.sh --zone=europe-west1-b reddit-app #This variant work with Google Cloud SDK Shell gcloud compute instances create --boot-disk-size=10GB --image=ubuntu-1604-xenial-v20170815a --image-project=ubuntu-os-cloud --machine-type=g1-small --tags puma-server --restart-on-failure --metadata-from-file startup-script=Startup.sh --zone=europe-west1-b reddit-app #This variant work with Cloud Shell and use file into server https://gist.github.com/Nonamed123/1e8afd0c2abab59994493d5e4506ee94 #This source for work script gcloud compute instance-templates create reddit-app --boot-disk-size=10GB --image=ubuntu-1604-xenial-v20170815a --image-project=ubuntu-os-cloud --tags puma-server --machine-type=g1-small --restart-on-failure --metadata startup-script='wget -O - https://gist.githubusercontent.com/Nonamed123/1e8afd0c2abab59994493d5e4506ee94/raw/4855c1fc2b0007ab619ba587309590bb540377c0/Script.txt | bash' #This variant use template, this vork variant
Three varian use for  application image: about puma as service, next puma scripts with rc.local and puma start with init.d use skeleton: use two varinat esay andmore dificult.
gcloud compute instances create reddit-app --image-family reddit-full --zone=europe-west1-b --tags puma-server --machine-type=g1-small --restart-on-failure - for first varian
gcloud compute instances create reddit-app --image-family reddit-apper --zone=europe-west1-b --tags puma-server --machine-type=g1-small --restart-on-failure - for second variant
gcloud compute instances create reddit-app --image-family reddit-dem --zone=europe-west1-b --tags puma-server --machine-type=g1-small --restart-on-failure - for third variant
gcloud compute instances create reddit-app --image-family reddit-test --zone=europe-west1-b --tags puma-server --machine-type=g1-small --restart-on-failure
