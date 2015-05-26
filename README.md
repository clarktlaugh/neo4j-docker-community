# Neo4j Community Docker Image

A nice, clean image of Neo4j Community with appropriate documentation. This image of Neo4j also allows users to mount their Neo4j ``data`` directory via:

# Try It Out

## Run (as a test)

- On the server that docker is installed: 
``docker pull clarktlaugh/neo4j-community``
- Then run your image!  Warning, this will expose the Neo4j brower to the outside word, it's just a test:
``docker run -d --name neo4j --privileged -p 7474:7474 -p 1337:1337 -v /tmp/neo4j:/var/lib/neo4j/data clarktlaugh/neo4j-community``
- Then navigate over to ``<yourIP/hostname>:7474`` to ensure your data browser works
- Create a node to test

## Run (in production)

Obviously in production you're going to want to not allow users to access :7474 (Neo4j browser) or access :1337 (Neo4j shell) so we can change the ``-p`` flag to ensure the ports are only exposed locally to the server.

``docker run -d --name neo4j --privileged -p 127.0.0.1:7474:7474 -p 127.0.0.1:1337:1337 -v /srv/neo4j-data:/var/lib/neo4j/data clarktlaugh/neo4j-community``
