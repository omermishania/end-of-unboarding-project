
# End of onboarding project

 1.  Create a simple web Python application (e.g., `Flask`)
 2.  Upload it to GitLab with `requirements.txt`, `Dockerfile`, etc.
 3.  For best practice, create manifests in a new different repository. `ArgoCD` will use these manifests to deploy your app. Create those in `Helm` templating format
(It should include templates for deployment, service, and route). 
Make it accessible from your browser for the next tasks
**EXTRA:** make it generic (read about `Helm Tpl function`)

 4.  Set up a GitLab CI/CD Pipeline, which whenever a new commit to the main branch is pushed, will:

	 1. Pylint your python code
	 2. Build and push an updated new image tag of your app (Create your own docker-hub repository if needed)
	 3. **EXTRA:** add a stage to the pipeline which will update the image tag at the manifests repository to the updated image tag every time a new tag of the image is pushed to the registry
	 4. **EXTRA:** add a webhook so that ArgoCD will refresh automatically whenever the image is updated at the manifests repository (You will be able to achieve this only after step 5 when ArgoCD is up)

5.  By implementing both extras, together with activating ArgoCD auto-sync, your app update process should now be fully automated!

6.  Deploy your app on ArgoCD
    
### Well Done!
