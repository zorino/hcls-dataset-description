HCLS Dataset Descriptions statistics scripts
====

## Statistics - hcls-dd.rb

Scripts to produce statistics over a SPARQL endpoint that are compliant with the W3C Dataset Descriptions for Health Care and Life Sciences (HCLS) as provided by the HCLS interest group. See https://www.w3.org/TR/hcls-dataset/

Note that the script will be computed the statistics for each graph in the endpoint individually.

``
ruby hcls-dd.rb


    hcls-dd.rb [options] <SPARQL url>

    Input:
       --uri               <endpoint uri>
       --sparql            <target sparql uri>
       --default-graph     <default graph uri>
       --label             <,'endpoint label'> [default: my_endpoint]
       --description       <'endpoint description'> [default: My Endpoint Statistics]

    Output:
       --output_json       <outfile.json> save hash as json file
       --output_rdf        <outfile.ttl>

    Options:
       --basic_metrics     to compute only the basic metrics

       --help              print this

``

The script will produce a ntriple graph file (for the dataset description) and a json file with all the stats that can be used with the types graph visualization widget as describe in the output section.

## Output - hcls-output.rb

``
ruby hcls-output.rb


hcls-output.rb <hcld-dd_output.json> <prefixes.tsv>

# The script needs json output from the hcls-dd.rb script.
# Will produce TSV statistics table for each graphs and a graph.js file
# that can be used by the types graph viewer

``

We highly recommend to use prefixes for all the type and predicate to get a cleaner visualization output.


## Example

See the ./example/ directory

