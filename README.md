# Amazon-KG dataset
This dataset provides information related to Amazon products with Dbpedia for cross-domain recommendation and currently includes two domains of Movie_and_TV and Books. This dataset consists of four parts as follows:
* `items`
    * items file.
    * Each line is a triplet (`iid`, `title` and `uri`) for one item, where `iid` represent the item ID in the original Amazon dataset, `title` represent the item name after regular expression transformation, and `uri` represent the matching DBpedia ID, respectively.

* `triples`
    * knowledge graph file
    * Each line is a triplet (`iid`, `head-entity`, `relation` and `tail-entity`), where `iid` represent the item ID in the original Amazon dataset. The knowledge graph is organized in Resource Description Framewor(RDF)/triples with data formalized as (`head-entity`, `relation` and `tail-entity`), which is used to represent a certain fact. For example, `B00005U13S	res:The_Vampire_Bat	dbo:director	res:Frank_R._Strayer` indicates that the item ID `B00005U13S` - `The_Vampire_Bat ` retrieved through DBpedia with its `director` as `Frank_R._Strayer`. We list the abbreviations and prefixes in the files as follows:
        ```
        res: http://dbpedia.org/resource/
        cat: http://dbpedia.org/resource/Category:
        dbo: http://dbpedia.org/ontology/
        dct: http://purl.org/dc/terms/
        dbr:  http://dbpedia.org/resource/
        rdfs: http://www.w3.org/2000/01/rdf-schema#
        yago: http://dbpedia.org/class/yago/
        rdf: http://www.w3.org/1999/02/22-rdf-syntax-ns#
        ```

* `item_metadata`
    * items metadata file.
    * Each line is a triplet (`iid` and `metadata`) for one item, where `iid` represent the item ID in the original Amazon dataset, `metadata` represent the information related to the item retrieved from DBpedia via the item linked entity, which can be viewed as an enhanced item profile.

* `ratings`
    * user-item interactions file
    * Each line is a user with her/his interactions with items: (`uid`, `iid` and `y`), where `uid` and `iid` represent the user and item ID in the original Amazon dataset respectively, and `y` represent the user rating for the item (ranging from 1 to 5).

We will publish the details of how to retrieve knowledge graphs based on recommendation data in our subsequent work. Thanks for the support.
