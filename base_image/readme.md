export IMAGE_NAME=basic-redis
docker build -t $IMAGE_NAME ./
TESTCONTAINERID=$(docker run -d --name $IMAGE_NAME-container -p 6379:6379 $IMAGE_NAME --save 60 1 --loglevel warning)
docker start $TESTCONTAINERID
