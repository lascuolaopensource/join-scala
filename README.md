# ✨JOIN✨

An open software for new Institutions, to empower <em>more-than-human</em> 
assemblages of commons (ideas, skills, tools) and people.

Mantained by [La Scuola Open Source](lascuolaopensource.xyz). 

## 👽 What is it? 

Join focuses on the process of production and reproduction of value (economic, cultural, social and symbolic) in self-organizing communities. 

The challenge of Join is to offer a product/platform to:
- Shorten the distances between communities that pursue the same values and facilitate the workability/feasibility of projects.
- Strengthen the cultural production activity of the new institutions.
- Give more control over their data to the participants.
- Provide an open source tool customized by all users according to the different communities.
- Provide a tool for horizontal, and not vertical, relationships between the communities that use it.


## 🧰 How to use it?

Join consists in:

- [Backend](https://github.com/lascuolaopensource/join-backend/tree/master) (Scala, Play Framework)
- [Admin](https://github.com/lascuolaopensource/join-frontend/tree/master) and [Public](https://github.com/lascuolaopensource/join-frontend/tree/master) frontends (Typescript, Angular, SASS)
- [Database](https://hub.docker.com/_/postgres) (PostgreSQL)

In addiction you have an [npm package](https://github.com/lascuolaopensource/join-ui-shared.git) for all shared ui styles between frontends.
Everything encapsuled via [Docker](docker.com) containers and ready to be deployed on a [Swarm](https://docs.docker.com/engine/swarm/), reverse proxying with [Traefik](https://containo.us/traefik/).

### Clone

In order to use Join you have to clone the repo and every submodule first.

Clone repository:

        git clone https://github.com/lascuolaopensource/join.git
  
Clone submodules:

        git submodule update --init --recursive

### Choose an environment

Now you have to choose your environment:

- #### [Development](https://github.com/lascuolaopensource/join/tree/master/dev) — Use this one to customize look or to develop new features locally.
- #### [Production](https://github.com/lascuolaopensource/join/tree/master/prod) — Use this to deploy Join online and serve it to your community.
