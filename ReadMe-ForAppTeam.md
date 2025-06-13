# Details on Updating Postgresql Application

This project leverages many services in order to have a working, robust container system that runs the application code for a postgresql server. These services include; Docker, AWS Codebuild, AWS EKS and runs on basic AWS networking components such as VPCs and EC2. The great thing about this is that whenever the app developers make a chane to their code and push to github it AWS will recognise this. 

It will:
    - package up your application via Docker
    - buildspec.yml file handles the process by telling codebuild what to do.
    - Create a new image and push the image to AWS ECR
    - EKS will/should auto pick the new image up as the tagging is set to take the image with latest as the tag.

# Developer Workflow

- Developers commit and push changes to GitHub.
- CodeBuild handles image builds and pushes without manual intervention.
- EKS manages rollout of the new version automatically.

# Important to know

If your application requires an image update &/or a python version update. The devops team will have to make a change to the Dockerfile  in order to package up your app using a later version of python. However this can only be done once proper testing has been carried out. Any issues or questions, please reach out to the devops team direct.