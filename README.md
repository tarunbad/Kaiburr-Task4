# Kaiburr-Task4
CI/CD Pipeline
Additional Steps (Optional):<br>
Docker Registry Push:<br>
Extend the workflow to push the Docker image to a container registry. For example, push to Docker Hub.<br>
- name: Push to Docker Hub
  run: |
    echo ${{ secrets.DOCKER_PASSWORD }} | docker login -u ${{ secrets.DOCKER_USERNAME }} --password-stdin
    docker tag your-docker-image-name ${{ secrets.DOCKER_USERNAME }}/your-docker-image-name
    docker push ${{ secrets.DOCKER_USERNAME }}/your-docker-image-name<br>
Ensure that you've set up Docker Hub credentials as secrets in your GitHub repository.<br>
Deployment:<br>
Extend the workflow to deploy your application to your Kubernetes cluster or any other target environment.<br>
- name: Deploy to Kubernetes
  run: kubectl apply -f kubernetes/
