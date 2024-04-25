# Multi container set up flow 
1. Push code to github
2. Travis automatically pushs repo
3. ______ builds a test image, tests code
4. ______ builds prod images
5. ______ pushes built prod images to Docker Hub
6. Travis pushes project to AWS EB
7. EB pulls image from Docker Hub, deploys