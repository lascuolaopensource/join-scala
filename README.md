# ✨JOIN✨

An <em>open source</em> platform  — <em>ecologic, radical and inclusive</em> — for new Cultural Institutions, co-created to empower <em>more-than-human</em> assemblages of commons (ideas, skills, tools) and people.

Mantained by [La Scuola Open Source](lascuolaopensource.xyz). 

## 👽 What is it? 

Join focuses on the process of production and reproduction of value (economic, cultural, social and symbolic) in self-organizing communities. 

The challenge is to offer people a product/platform to:
- Shorten the distances between communities that pursue the same values and facilitate the workability/feasibility of projects.
- Strengthen the cultural production activity of indipendent organizations.
- Give participants more control over their data. 
- Provide an open source tool customized by all users according to the different communities.
- Provide a tool for horizontal relationships between the communities members that use it.

### 🌟 Why a new platform?

Everything we do on the Internet has a cost.
And the only thing we all have in the same way is our time.

Personal data, social relationships and attention have become the new currency.
Ignoring it means giving up an essential part of our time in exchange for indispensable services.
This mechanism occurs almost unconsciously and is considered inessential.
Located at the crossroads of technology, politics and economics, the digital platform model is currently the most advanced form of mediation between supply and demand in the global market.

But what exactly is a platform, and why do we need to build, use and relate new platforms?

Platforms, unlike factories, produce nothing, but create value by mediating social and technological relationships. In other words, platforms stand in the middle of any relationship between two or more elements.
This may seem very abstract, but in reality it happens constantly every time you use a social network to communicate and get information, buy items, watch a movie, order a pizza or look for a house for rent.
Mediation takes place in an opaque way, because the technology that makes the platforms work is private and very complex. The material archive where the components that make this technology possible is also private (the server) as well as the interface, or the visual facade of each platform.

We believe that everyone, regardless of the level of understanding of new technologies, should have full control of the platforms they use.

### 💞 Communicate, share, organize

In recent years we have witnessed a fence of online activities increasingly controlled by a few proprietary platforms.

Any type of activity, whether it is communicating with friends, managing an information channel to a certain audience, or collectively organizing projects, takes place on platforms not specifically designed for that purpose, nor designed by those who use them.

An exemplary case is given by the inability to control the continuous flow of messages from a bulletin board or an instant messaging application. The architecture of a platform, which defines the experience of those who use it, is not neutral, but determines how you are on that platform and how you relate to it. The interfaces control our mood, through an alternation of positive and negative stimuli (excitement and depression), which can lead to situations of narcissistic competition.

In this context, addressing individuals and collectives that start from our own needs, we have built a useful tool for organization and communication in the field of cultural production, aware that the architecture of the platform itself will encourage collaboration, inclusion and horizontality at the expense of competition, exclusion and hierarchies of gender, race, class and training.

### 🌈 Joining Join

Join is not just an online portal, but first of all a support tool for an ecosystem made up of social spaces, cultural centers, collectives and individuals.
Joining Join means exploring the unpredictable possibilities that interconnection between humans can generate.

If you want to learn more about Join, read our Wiki (add link).

## 🧰 How to use it?

Join consists in:

- [Backend](https://github.com/lascuolaopensource/join-backend/tree/master) (Scala, Play Framework)
- [Admin](https://github.com/lascuolaopensource/join-frontend/tree/master) and [Public](https://github.com/lascuolaopensource/join-frontend/tree/master) frontends (Typescript, Angular, SASS)
- [Database](https://hub.docker.com/_/postgres) (PostgreSQL)

In addiction you have an [npm package](https://github.com/lascuolaopensource/join-ui-shared.git) for all shared ui styles between frontends.
Everything encapsuled via [Docker](docker.com) containers and ready to be deployed on a [Swarm](https://docs.docker.com/engine/swarm/), reverse proxying with [Traefik](https://containo.us/traefik/).

### 👥 Clone

In order to use Join you have to clone the repo and every submodule first.

Clone repository:

        git clone https://github.com/lascuolaopensource/join.git
  
Clone submodules:

        git submodule update --init --recursive

### 🌱 Choose an environment

Now you have to choose your environment:

- #### 💻 [Development](https://github.com/lascuolaopensource/join/tree/master/dev) - Use this one to customize look or to develop new features locally.
- #### 💪🏾 [Production](https://github.com/lascuolaopensource/join/tree/master/prod) - Use this to deploy Join online and serve it to your community.
