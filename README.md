# study_jam_team_two_vm_deployment_git-
Place your project id in the place marked <place-your-project-id-here>
Place your zone name in the place marked <place-your-zone-here>
Place your sevice account email where your find <place-your-service-account-email-here >

To find your service account you can run this command in your gcloud shell :

gcloud compute project-info describe --project PROJECT_ID

And copy the 'defaultServiceAccount' and place it where you find <place-your-service-account-email-here >

	
upload the team_two_network_firewall_vm_general.jinja file to gcloud shell


RUN gcloud deployment-manager deployments create team-two-quickstart-deployment --template team_two_network_firewall_vm_general.jinja

Go to compute engine >>vm instances and then ssh into the team-two-vm instance

RUN sudo git clone https://github.com/EvansAF/team-two-names-api.git

cd into team-two-names-api

RUN sudo npm install

RUN PORT=8080 DEBUG=team-two-names-api* npm start



Visit the vm external ip with the port 8080 appended 

http://<IP_ADDRESS>:8080/


TO DELETE

RUN gcloud deployment-manager deployments delete team-two-quickstart-deployment
OR  go to the deployment manager console section click delete, select the option to have every resource deleted
