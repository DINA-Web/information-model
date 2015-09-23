
![DINA-Web Logo](http://www.dina-project.net/w/media/thumb/1/14/DINALogo.png/272px-DINALogo.png)

This space captures discussions about the information model and ideas about changes. Please add your materials to this repo!

# Exposing the Information Model through Web APIs


## Module map - high level system overview

The modules.odg is of historical interest as a high level map over some important data types and services in the DINA system....

![Module Map](dina-modules.png)

## Important data types and services

```console

  Some core data types     Some associations to other data types
  (NOUNS)
 +-----------------------+
 |  CollectionObject     | incl "containers" and links to media, projects
 +-----------------------+ catalogues, collection, determinations etc
 +-----------------------+
 |   Taxon / taxonomy    | determinations, links to most other data types
 +-----------------------+
 +-----------------------+
 |  Locality / places    | links to geography, collecting events, ref works,
 +-----------------------+ habitat, stratigraphy
 +-----------------------+
 |  Storage location     | space (time?) coord for physical storage location
 +-----------------------+
 +-----------------------+
 |   User/Agent/People   | incl org/group links, generates events such as
 +-----------------------+ determinations, accessions, loans etc
 +-----------------------+
 |  Reference work       | citations
 +-----------------------+
 +-----------------------+
 |  Media (binary assets)| depictions, sounds and other associated objects
 +-----------------------+

 Higher level web APIs expose functionality needed for compound tasks, such as
   - reporting / statistics / printing etiquettes etc
   - "workbench" type functionality for migrating data in and out
   - managing collections including loans, data entry etc

 Web UI components provide clients or front-end to support these tasks
 interactively and while doing so work against backend web APIs.
 +-----------------------+
 |   DNA (LIMS seqs etc) |
 +-----------------------+
 +-----------------------+
 |   Species Profile     | links text and images to a taxon,
 +-----------------------+ describes habitat, behaviour etc

# Text diagrams can be created with JavE
# src: http://www.jave.de/download/download.html 
# cmd: java -jar jave5.jar
```

## Web UIs versus Web APIs - overview of DINA architecture

```console

   FRONT-ENDS / CLIENTS / WEB UIs

   +------------------+ +---------------+ +-----------------+ +----------------+
   |Coll Data Entry XL| |Species Profile| |DNA Seq Mgm      | |Loans from Coll |
   +------------------+ +---------------+ +-----------------+ +----------------+
   +-------------------+ +--------------------+  +---------+  +----------------+
   |Geological Coll Mgm| |Search UI for Colls |  |Support  |  |Loans Mgm       |
   +-------------------+ +--------------------+  +---------+  +----------------+
                        +-----------------------+
    The UIs above       | General Collections   |
    exist but not ->    | Mangament Web UI      |
                        +-----------------------+

  ----------------------------DINA Web APIs--------------------------------------

  BACK-ENDS / SERVERS / WEB APIs

  +-------------+  +-------------+ +----------+ +-------------+  +-------------+
  |Taxonomy API |  |DNA Seq API  | | SPM API  | |Coll Mgm API |  |Media API    |
  +-------------+  +-------------+ +----------+ +-------------+  +-------------+

  The APIs       +---------+  +-------------+  +-------------+   +--------------+
 above exist     |User API |  |Locality API |  |Storage API  |   | Batch IO API |
but not these -> +---------+  +-------------+  +-------------+   +--------------+

```

### Current Web UIs / clients / front-ends 

The following UI components are currently available and make use of the backend web APIs:

- [Species Information](https://dina-web.net/naturalist)
- [Public Loans from Collections](https://dina-web.net/loan)
- [Managing Loans in Collections](https://dina-web.net/loan-admin)
- [Batch Data Entry into Collections through Excel](https://dina-web.net/inventory)
- [Linking data to Collections using DNA](https://dina-web.net/dnakey)
- [Searching across Collections](https://dina-web.net/naturarv)

- [Operational Support (Tickets etc) for DINA-Web](https://issues.dina-web.net)


### Current Web APIs / servers / back-ends

Existing modules and their respective doucumented web APIs:

- [Taxonomy management](https://github.com/TU-NHM/plutof-taxonomy-module) 
- [DNA data web APIs from *seqdb*](no online docs yet) *DOCS IN PROGRESS*
- [Species Profile Model API in The Naturalist](https://dina-web.net/naturalist/api)
- [Media API](https://github.com/DINA-Web/mediaserver-module/blob/master/docs/new-api.md) *DOCS IN PROGRESS*
- [DINA Specify REST API](no online docs yet) *DOCS IN PROGRESS*
- [Dina Data Tool](no online docs yet) *DOCS IN PROGRESS*

### Current CLI Tools

- [CollectionBatchTool](http://collectionbatchtool.readthedocs.org/en/latest/)


## Guidelines and principles of construction

Here are information about various guidelines and principles of construction that inspire and guide the construction, design and future development of `DINA-Web`:

- [Functional guidelines - API design guidelines](https://github.com/DINA-Web/dina-api-standard)
- [Style guidelines - Visual design guidelines](https://DINA-Web.github.io/style.html)
- [Licensing guidelines](https://DINA-Web.github.io/licensing.html)
- [Data exchange guidelines - Import and export of data](https://github.com/DINA-Web/batch-import)

# System diagram for DINA-Web components

![System diagram](dina-diagram.png)

# DINA-Web infrastructure

Please see [Infrastructure](infrastructure.Rmd) for an overview of the technology stack that the DINA system runs on.
