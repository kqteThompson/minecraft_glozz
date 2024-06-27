# Minecraft dialogues
#### from splits in 2020 Jayannavar et al. ***Learning to execute instructions in a Minecraft dialogue***
[paper](https://aclanthology.org/2020.acl-main.232.pdf)

#### the annotations are described in Thompson et al. ***Discourse structure for the Minecraft dialogue corpus***
[paper](https://aclanthology.org/2024.lrec-main.444.pdf)

#### and can be found in json format here:
https://github.com/linagora-labs/MinecraftStucturedDialogueCorpus


## Glozz annotation tool
This is a tool built in Java that you can download from the Glozz [website](http://www.glozz.org/). If you dont want to install locally you can run it with Docker (see below). 
If you want to be able to save your annotations you will need to email the authors to request a login key (see website).

### Glozz directory structure

* **annotation__tool/**
    * Dockerfile
    * docker-compose.yml
    * start.sh
    * glozz-platform.jar (downloaded from glozz)
    * data/
        * annotationModels/
            * ccbts.aam
        * annotations/
            * dialogue_id.aa 
        * corpus
            * dialogue_id.ac
        * styles
            * ccbts.as

 NB: in order to see an annotated dialogue you will need one .aa file and one .ac file for that dialogue, which must be in the data/annotations/ and the data/corpus/ directories respectively. The annotations are stored in the .aa file. Annotation_tool/ already contains a sample dialogue from the dev split. 


### Running Glozz with Docker
1. Make sure [docker and docker-compose](https://docs.docker.com/get-docker/) are installed.

2. From the directory downloaded from the Glozz website, move the .jar file to the annotation_tool directory

3. Build the docker container (you only need to do this once)

    ```
    docker build --tag "my-glozz" -f Dockerfile .
    ```

4. To run the container each time use the bash file to run docker-compose. 

    ```
    sh start.sh
    ```

When you close the glozz window docker will stop automatically.



