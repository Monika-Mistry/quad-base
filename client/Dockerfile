#Use a base node image
FROM node:latest AS node-build
#copy contents into image
COPY . .
#execute command to download dependancies
RUN npm install
# execute command to construct node project
RUN npm run build
# use a new image
FROM node:latest AS node-serve
# copy through the build directory created in a previous step
COPY --from=node-build /build/build .
# run the command to download dependacies - but append it with -g serve
RUN npm install -g serve
# create an entrypoint instruction - it will take 3 arguments "serve"(make sure you get the correct location), "-l", and a port number
ENTRYPOINT ["serve","-l",85]
