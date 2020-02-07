# private

1. Clone the Digikube repository
2. Login to GCP console
3. Create new project
4. Start Google Cloud Shell.  If the shell does not start in the newly created project then switch to the newly created project.
5. Execute the following command to deploy Digikube on GCE
  
      #Replace the repo url by the repo you have created (by cloning digikube)

      digikubeCodeRawRepoUrl="https://raw.githubusercontent.com/samdesh-gcp1/digikube/master";
      digikubeInstanceRawRepoUrl="https://raw.githubusercontent.com/samdesh-gcp1/c1-dev1/master";
      tmpExecDir=$(mktemp -d --suffix="-digikube");
      bootstrapShell="${tmpExecDir}/bootstrap";
      wget -q --no-cache -O ${bootstrapShell} - "${digikubeCodeRawRepoUrl}/cloud-init/bootstrap";
      chmod +x ${bootstrapShell};
      ${bootstrapShell} ${digikubeCodeRawRepoUrl} ${digikubeInstanceRawRepoUrl} create;
      rm -rf "${tmpExecDir}"
  
  
6. Execute the following command to delete Digikube on GCE

      #Replace the repo url by the repo you have created (by cloning digikube)
      
      digikubeCodeRawRepoUrl="https://raw.githubusercontent.com/samdesh-gcp1/digikube/master";
      digikubeInstanceRawRepoUrl="https://raw.githubusercontent.com/samdesh-gcp1/c1-dev1/master";
      tmpExecDir=$(mktemp -d --suffix="-digikube");
      bootstrapShell="${tmpExecDir}/bootstrap";
      wget -q --no-cache -O ${bootstrapShell} - "${digikubeCodeRawRepoUrl}/cloud-init/bootstrap";
      chmod +x ${bootstrapShell};
      ${bootstrapShell} ${digikubeCodeRawRepoUrl} ${digikubeInstanceRawRepoUrl} delete --forced,
      rm -rf "${tmpExecDir}"
