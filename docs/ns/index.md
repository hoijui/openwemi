
<!DOCTYPE html>
<html>
  <head>
    <title>openWEMI ontology</title>
    <style>
        #pylode {
            position: fixed;
            top: 205px;
            left: -150px;
            font-size: small;
            transform: rotate(-90deg);
            color: grey;
        }
        #pylode a {
            font-size: 1.5em;
            font-weight: bold;
            text-decoration: none;
            color: #005A9C;
        }
        #pylode a:hover {
            color: #333;
        }
        #pylode #p {
            color: #329545;
        }
        #pylode #y {
            color: #f9cb33;
        }
        #pylode #version {
            font-size: 1.0em;
        }

        #profile {
            font-style: italic;
            font-size: 1.25em;
            color: darkred!important;
        }

        .cardinality {
            font-style: italic;
            color: #aa00aa;
        }

        dl {
            /*border: 1px solid navy;*/
            /*padding:5px;*/
        }

        dt {
            font-weight: bold;
            padding: 0;
        }

        dd {
            margin-bottom: 10px;
            padding-top: 7px;
        }

        #metadata ul,
        #classes ul {
            list-style-type: none;
        }

        #metadata ul li,
        #classes ul li {
            margin-left: -40px;
        }

        ul.hlist {
            list-style-type: none;
            border: 1px solid navy;
            padding:5px;
            background-color: #F4FFFF;
        }

        ul.hierarchy {
            border: 1px solid navy;
            padding: 5px 25px 5px 25px;
            background-color: #F4FFFF;
        }


        ul.hlist li {
            display: inline;
            margin-right: 10px;
        }

        .entity {
            border: 1px solid navy;
            margin:5px 0 5px 0;
            padding: 5px;
        }

        .entity th {
            width: 150px;
            vertical-align: top;
        }

        .entity th,
        .entity td {
            padding-bottom: 20px;
        }

        .entity table th {
            text-align: left;
        }

        section#overview img {
            max-width: 1000px;
        }

        h1, h2, h3, h4, h5, h6 {
            text-align: left
        }
        h1, h2, h3 {
            color: #005A9C; background: white
        }
        h1 {
            font: 170% sans-serif;
            line-height: 110%;
        }
        h2 {
            font: 140% sans-serif;
            margin-top:40px;
        }
        h3 {
            font: 120% sans-serif;
            margin-top: 20px;
            padding-bottom: 5px;
            border-bottom: 1px solid navy;
        }
        h4 { font: bold 100% sans-serif }
        h5 { font: italic 100% sans-serif }
        h6 { font: small-caps 100% sans-serif }

        body {
            padding: 2em 70px 2em 70px;
            margin: 0;
            font-family: sans-serif;
            color: black;
            background: white;
            background-position: top left;
            background-attachment: fixed;
            background-repeat: no-repeat;
            text-align: left;
        }

        section {
            max-width: 1500px;
        }

        .figure {
            margin-bottom: 20px;
        }

        :link { color: #00C; background: transparent }
        :visited { color: #609; background: transparent }
        a:active { color: #C00; background: transparent }

        .sup-c,
        .sup-op,
        .sup-fp,
        .sup-dp,
        .sup-ap,
        .sup-p,
        .sup-ni,
        .sup-con,
        .sup-col {
            cursor:help;
        }

        .sup-c {
            color:orange;
        }

        .sup-op {
            color:navy;
        }

        .sup-fp {
            color:lightskyblue;
        }

        .sup-dp {
            color:green;
        }

        .sup-ap {
            color:darkred;
        }

        .sup-p {
            color:black;
        }

        .sup-ni {
            color:brown;
        }

        .sup-con {
            color:orange;
        }

        .sup-col {
            color:darkred;
        }

        sup {
            margin-left: -3px;
        }
        code {
            font-size: large;
            color: darkred;
        }

        /* less prominent links for properties */
        .proplink {
            color: #336;
            text-decoration: none;
        }

#toc {
    position: fixed;
    top: 0;
    right: 0;
    z-index: 2;
    height: 100%;
    overflow-y: auto;
    padding: 10px;
    border: solid 1px navy;
    font-size: small;
    width: 180px;
}
#toc h3 {
    margin-top: 5px;
}

#toc ul {
    list-style: none;
    padding-left: 0;
}

#toc .first > li {
    margin-top: 5px;
}

#toc .second,
#toc .third {
    padding-left: 10px;
}

#content {
    width: calc(100% - 150px);
}

.hover_property {
    cursor: help;
    text-decoration: none;
    border-bottom: dashed 1px;
}

.setclass {
    list-style-type: none;
}

code{
    word-wrap: break-word;
  }
table {
    table-layout: fixed;
    width: 100%;
}
td {
    word-wrap: break-word;
}
#legend table.entity {
    width: 25%;
}
	</style>
    <link href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAABhklEQVQ4jbWPzStEURjG3yQLirlGKUnKFO45Z+SjmXvnnmthQcpCoVhYmD/AwmJiI3OvZuZc2U3UlKU0/gAslMw9JgvhHxAr2fko7r0jHSsl+TgbTz2Lt5731/MASEiJW9ONml2QyX6rsGalmnT74v8BDf12hxJfpV8d1uwNKUBYszabdFv84L8B9X0rESVmmUup2fme0cVhJWaZHw4NWL1SewEAfDe6H3Dy6Ll456WEJsRZS630MwCAOI20ei5OBpxse5zcBZw8eS4uPpfIuDiCainIg9umBCU0GZzgLZ9Hn31OgoATL+CkLDGB5H1OKj4nFd/FBxUXJ0UZNb4edw/6nLyJXaj5FeCVyPLNIVmYK8TG1IwWb16L1gEACAFV90ftoT8bdOX0EeyY99gxBXZMgRz6qGb1KantAACI0UvE6F5XJqEjpsdURouI0Vt5gGOUkUNnPu7ObGIIMfNaGqDmjDRi9FZldF1lRgYzeqUyeoiY4ag5Iy3RgOYRM8+/M2bG8efsO4hGrpmJseyMAAAAAElFTkSuQmCC" rel="icon" sizes="16x16" type="image/png">
    <link href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAgCAYAAABzenr0AAAC40lEQVRYhe2UT0hUQRzHp6Iss1B3VZKIDbbdfW9mnoi4f3zzjkJQeOgS0SEIb1EWBGGlLLu460zQPQM1unUIIjA6rfpm6ZAhHjoIRVQUFUlEbG+euTsdXG1d3VL3bVD4g+9h+L35fT/8fvN7ADgY9aHY5fpIvK82HO9ysu66wxWOzbkjcekKx0a2ALYA/n2AGi3a6ArFezcidziecQygNhhrcUficjP6PwBqtGijKxy/thnVBePHywYoDsFhl53GV8SEcsTx4usCMLUewTVpc23BNvEzm6Neyf1+KcG2vwqwUjgrOJq2JmHftwmkVBRGTvncFodnbI7vChO/FRznCmHsNM7aHM9Yk7Df5iqsLMw9sMNOK2g+jS4IEz0UJv4iuJZb2RltWnB4UZqH6ioGAgAAGe5vtiZhtzDx7OoRadLmeM7m6IRjhnLMW2Vx1bA5GhAmnhIcz6/xNj4Ujsky8UspwfayjDPjsF2Y6L7N8Vzx/BfP+KPg6LbgSqd8DnfJW2CnbaLhfH5ephpqygJYvQU4Z3P82TLRsDDhUTnmrSq+Y3N0Mg+Xldy/zwEAnLMWZ3pHpNExmfLs/t0dOdVcbT0JeKxUwFP2VljjqiE47Jp53LTXNxhsUZjerTByXWX6VZWRs/4bIQ2ACv+UAomgDzLCISNZxAxZKMhIDjLy1JfsaK+I+eGBUBNk5E2x8RogX/PdcDZUqieWTSh5D6nOVKqfhoycUmlHFFIyu5RXqf7AcQDISCpv/tqbMBqK883RtmpISRoxQyJKPgGn3wNk5NEigDFa6hslqV/Kj+FdBQD0bshIDlKSLlVcoWQo36UhR80BAMB73lulMn0EMpJTqD6qJiOt3mho/8GbkT2BZNgDB/V+RI0fkOrT3kRIVQbaDizJm2hdNbINBxwk5xAj3yEjuV9rZ1iIkgxixkLBA83mz8uCjLwoGwAx0vOnFSy5mtR4VTaAQvVORMnwZgSpzkrV/QmdE2tKe46+MQAAAABJRU5ErkJggg==" rel="icon" sizes="32x32" type="image/png">
    <meta content="text/html; charset=utf-8" http-equiv="Content-Type">
    <script id="schema.org" type="application/ld+json">
[
  {
    "@id": "https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#",
    "@type": [
      "https://schema.org/DefinedTermSet"
    ],
    "https://schema.org/name": [
      {
        "@value": "openWEMI ontology"
      }
    ]
  }
]
	</script>
  </head>
  <body>
    <div id="content">
      <div class="section" id="metadata">
        <h1>openWEMI ontology</h1>
        <h2>Metadata</h2>
        <dl>
          <div>
            <dt>
              <strong>IRI</strong>
            </dt>
            <dd>
              <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#</code>
            </dd>
          </div>
          <div>
            <dt>
              <a class="hover_property" href="http://purl.org/dc/terms/title" title="A name given to the resource. Defined in DCMI Metadata Terms">Title</a>
            </dt>
            <dd><p>openWEMI ontology</p></dd>
          </div>
        </dl>
      </div>
      <div class="section" id="classes">
        <h2>Classes</h2>
        <div class="property entity" id="Endeavor">
          <h3>Endeavor
            <sup class="sup-c" title="OWL/RDFS Class">c</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#Endeavor</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>A creation.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inDomainOf" title="Inverse of rdfs:domain. Defined in Ontology Documentation Profile">In Domain Of</a>
              </th>
              <td>
                <span>
                  <a href="#responsibleEntity">responsible entity</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/superClassOf" title="Inverse of RDFS' subClassOf. Defined in Ontology Documentation Profile">Super Class Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#Work">Work</a>
                      <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#Expression">Expression</a>
                      <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#Manifestation">Manifestation</a>
                      <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#Item">Item</a>
                      <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="Work">
          <h3>Work
            <sup class="sup-c" title="OWL/RDFS Class">c</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#Work</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>An abstract notion of an artistic or intellectual creation.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subClassOf" title="The subject is a subclass of a class. Defined in The RDF Schema vocabulary (RDFS)">Sub Class Of</a>
              </th>
              <td>
                <span>
                  <a href="#Endeavor">Endeavor</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inDomainOf" title="Inverse of rdfs:domain. Defined in Ontology Documentation Profile">In Domain Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#relatedWork">related Work</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#expressedBy">expressed by</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inRangeOf" title="Inverse of rdfs:range. Defined in Ontology Documentation Profile">In Range Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#relatedWork">related Work</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#expresses">expresses</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="Expression">
          <h3>Expression
            <sup class="sup-c" title="OWL/RDFS Class">c</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#Expression</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>A perceivable form of the creation.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subClassOf" title="The subject is a subclass of a class. Defined in The RDF Schema vocabulary (RDFS)">Sub Class Of</a>
              </th>
              <td>
                <span>
                  <a href="#Endeavor">Endeavor</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inDomainOf" title="Inverse of rdfs:domain. Defined in Ontology Documentation Profile">In Domain Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#relatedExpression">related Expression</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#expresses">expresses</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inRangeOf" title="Inverse of rdfs:range. Defined in Ontology Documentation Profile">In Range Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#relatedExpression">related Expression</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#expressedBy">expressed by</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="Manifestation">
          <h3>Manifestation
            <sup class="sup-c" title="OWL/RDFS Class">c</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#Manifestation</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>The physical embodiment of a creation.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subClassOf" title="The subject is a subclass of a class. Defined in The RDF Schema vocabulary (RDFS)">Sub Class Of</a>
              </th>
              <td>
                <span>
                  <a href="#Endeavor">Endeavor</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inDomainOf" title="Inverse of rdfs:domain. Defined in Ontology Documentation Profile">In Domain Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#relatedManifestation">related Manifestation</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#manifests">manifests</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inRangeOf" title="Inverse of rdfs:range. Defined in Ontology Documentation Profile">In Range Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#relatedManifestation">related Manifestation</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#manifestedBy">manifested by</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="Item">
          <h3>Item
            <sup class="sup-c" title="OWL/RDFS Class">c</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#Item</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>An exemplar of a creation.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subClassOf" title="The subject is a subclass of a class. Defined in The RDF Schema vocabulary (RDFS)">Sub Class Of</a>
              </th>
              <td>
                <span>
                  <a href="#Endeavor">Endeavor</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inDomainOf" title="Inverse of rdfs:domain. Defined in Ontology Documentation Profile">In Domain Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#relatedItem">related Item</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#instantiates">instantiates</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="https://w3id.org/profile/ontdoc/inRangeOf" title="Inverse of rdfs:range. Defined in Ontology Documentation Profile">In Range Of</a>
              </th>
              <td>
                <ul>
                  <li>
                    <span>
                      <a href="#relatedItem">related Item</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                  <li>
                    <span>
                      <a href="#instantiatedBy">instantiated by</a>
                      <sup class="sup-p" title="RDF Property">p</sup>
                    </span>
                  </li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
      </div>
      <div class="section" id="properties">
        <h2>Properties</h2>
        <div class="property entity" id="responsibleEntity">
          <h3>responsible entity
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#responsibleEntity</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>One responsible for the creation, production, distribution, maintenance, or ownership of a created entity.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Endeavor">Endeavor</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="relatedWork">
          <h3>related Work
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#relatedWork</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>Another Work that is related in some way to a Work.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Work">Work</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td>
                <span>
                  <a href="#Work">Work</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="relatedExpression">
          <h3>related Expression
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#relatedExpression</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>Another Expression that is related in some way to an Expression.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Expression">Expression</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td>
                <span>
                  <a href="#Expression">Expression</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="relatedManifestation">
          <h3>related Manifestation
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#relatedManifestation</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>Another Manifestation that is related in some way to a Manifestation.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Manifestation">Manifestation</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td>
                <span>
                  <a href="#Manifestation">Manifestation</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="relatedItem">
          <h3>related Item
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#relatedItem</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>Another Item that is related in some way to an Item.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Item">Item</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td>
                <span>
                  <a href="#Item">Item</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="expresses">
          <h3>expresses
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#expresses</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>An Endeavor that expresses a Work.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Expression">Expression</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td>
                <span>
                  <a href="#Work">Work</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="expressedBy">
          <h3>expressed by
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#expressedBy</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>An Expression of a Work.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Work">Work</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td>
                <span>
                  <a href="#Expression">Expression</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="manifests">
          <h3>manifests
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#manifests</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>An Endeavor that manifests an Expression or a Work.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Manifestation">Manifestation</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td><span>
  <a href="#Expression">Expression</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span> <span class="cardinality">or</span> <span>
  <a href="#Work">Work</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span></td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="manifestedBy">
          <h3>manifested by
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#manifestedBy</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>A Manifestation of a Work or an Expression.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td><span>
  <a href="#Expression">Expression</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span> <span class="cardinality">or</span> <span>
  <a href="#Work">Work</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td>
                <span>
                  <a href="#Manifestation">Manifestation</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="instantiates">
          <h3>instantiates
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#instantiates</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>An Endeavor that instantiates a Manifestation, an Expression or a Work.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td>
                <span>
                  <a href="#Item">Item</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td><span>
  <a href="#Manifestation">Manifestation</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span> <span class="cardinality">or</span> <span>
  <a href="#Expression">Expression</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span> <span class="cardinality">or</span> <span>
  <a href="#Work">Work</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span></td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="instantiatedBy">
          <h3>instantiated by
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#instantiatedBy</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td><p>An instantiation of a Manifestation, an Expression or a Work.</p></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#subPropertyOf" title="The subject is a subproperty of a property. Defined in The RDF Schema vocabulary (RDFS)">Sub Property Of</a>
              </th>
              <td>
                <span>
                  <a href="http://purl.org/dc/terms/relation">Relation</a>
                  <sup class="sup-p" title="RDF Property">p</sup>
                </span>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#domain" title="A domain of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Domain</a>
              </th>
              <td><span>
  <a href="#Expression">Expression</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span> <span class="cardinality">or</span> <span>
  <a href="#Work">Work</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span> <span class="cardinality">or</span> <span>
  <a href="#Manifestation">Manifestation</a>
  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
</span></td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#range" title="A range of the subject property. Defined in The RDF Schema vocabulary (RDFS)">Range</a>
              </th>
              <td>
                <span>
                  <a href="#Item">Item</a>
                  <sup class="sup-c" title="OWL/RDFS Class">c</sup>
                </span>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="commonEndeavor">
          <h3>common Endeavor
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#commonEndeavor</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td>
                <ul>
                  <li><p>Relates any two resources that are or contain the same endeavor.</p></li>
                  <li><p>commonEndeavour is intended to define a relationship between two resources that may or may not be modeled as openWEMI. This makes it possible to assert that a resource modeled using a vocabulary that does not use the openWEMI entity model explicitly is describing the same Work, Expression, Manifestation, and/or Item as another resource.</p></li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="commonWork">
          <h3>common Work
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#commonWork</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td>
                <ul>
                  <li><p>Relates any two resources that are or contain the same Work.</p></li>
                  <li><p>commonWork is intended to define a relationship between two resources that may or may not be modeled as openWEMI. This makes it possible to assert that a resource modeled using a vocabulary that does not use the openWEMI entity model explicitly is describing the same Work, Expression, Manifestation, and/or Item as another resource.</p></li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="commonExpression">
          <h3>common Expression
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#commonExpression</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td>
                <ul>
                  <li><p>Relates any two resources that are or contain the same Expression.</p></li>
                  <li><p>commonExpression is intended to define a relationship between two resources that may or may not be modeled as openWEMI. This makes it possible to assert that a resource modeled using a vocabulary that does not use the openWEMI entity model explicitly is describing the same Work, Expression, Manifestation, and/or Item as another resource.</p></li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="commonManifestation">
          <h3>common Manifestation
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#commonManifestation</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td>
                <ul>
                  <li><p>Relates any two resources that are or contain the same Manifestation.</p></li>
                  <li><p>commonWork is intended to define a relationship between two resources that may or may not be modeled as openWEMI. This makes it possible to assert that a resource modeled using a vocabulary that does not use the openWEMI entity model explicitly is describing the same Work, Expression, Manifestation, and/or Item as another resource.</p></li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
        <div class="property entity" id="commonItem">
          <h3>common Item
            <sup class="sup-p" title="RDF Property">p</sup>
          </h3>
          <table>
            <tr>
              <th>IRI</th>
              <td>
                <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#commonItem</code>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://www.w3.org/2000/01/rdf-schema#isDefinedBy" title="The definition of the subject resource. Defined in The RDF Schema vocabulary (RDFS)">Is Defined By</a>
              </th>
              <td>
                <a href="https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#">openWEMI ontology</a>
              </td>
            </tr>
            <tr>
              <th>
                <a class="hover_property" href="http://purl.org/dc/terms/description" title="An account of the resource. Defined in DCMI Metadata Terms">Description</a>
              </th>
              <td>
                <ul>
                  <li><p>Relates any two resources that are or contain the same Item.</p></li>
                  <li><p>commonWork is intended to define a relationship between two resources that may or may not be modeled as openWEMI. This makes it possible to assert that a resource modeled using a vocabulary that does not use the openWEMI entity model explicitly is describing the same Work, Expression, Manifestation, and/or Item as another resource.</p></li>
                </ul>
              </td>
            </tr>
          </table>
        </div>
      </div>
      <span>
        <a href="#Work">Work</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Expression">Expression</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Work">Work</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Expression">Expression</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Work">Work</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Expression">Expression</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Manifestation">Manifestation</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Work">Work</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Expression">Expression</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <span>
        <a href="#Manifestation">Manifestation</a>
        <sup class="sup-c" title="OWL/RDFS Class">c</sup>
      </span>
      <div id="namespaces">
        <h2>Namespaces</h2>
        <dl>
          <dt id="dct">dct</dt>
          <dd>
            <code>http://purl.org/dc/terms/</code>
          </dd>
          <dt id="openwemi">openwemi</dt>
          <dd>
            <code>https://raw.githubusercontent.com/dcmi/openwemi/main/vocab/openWEMI.ttl#</code>
          </dd>
          <dt id="owl">owl</dt>
          <dd>
            <code>http://www.w3.org/2002/07/owl#</code>
          </dd>
          <dt id="rdf">rdf</dt>
          <dd>
            <code>http://www.w3.org/1999/02/22-rdf-syntax-ns#</code>
          </dd>
          <dt id="rdfs">rdfs</dt>
          <dd>
            <code>http://www.w3.org/2000/01/rdf-schema#</code>
          </dd>
          <dt id="skos">skos</dt>
          <dd>
            <code>http://www.w3.org/2004/02/skos/core#</code>
          </dd>
        </dl>
      </div>
      <div id="legend">
        <h2>Legend</h2>
        <table class="entity">
          <tr>
            <td>
              <sup class="sup-c" title="OWL/RDFS Class">c</sup>
            </td>
            <td>Classes</td>
          </tr>
          <tr>
            <td>
              <sup class="sup-p" title="RDF Property">p</sup>
            </td>
            <td>Properties</td>
          </tr>
        </table>
      </div>
    </div>
    <div id="pylode">
      <p>made by 
        <a href="https://github.com/rdflib/pyLODE">
          <span id="p">p</span>
          <span id="y">y</span>
          <span>LODE</span>
        </a>
        <a href="https://github.com/rdflib/pyLODE/release/3.0.6a" id="version">3.0.6a</a>
        <span> with the </span>
        <a href="https://w3id.org/profile/ontpub" id="profile">OntPub</a>
        <span>profile</span>
      </p>
    </div>
    <div id="toc">
      <h3>Table of Contents</h3>
      <ul class="first">
        <li>
          <h4>
            <a href="#metadata">Metadata</a>
          </h4>
        </li>
        <li>
          <h4>
            <a href="#classes">Classes</a>
          </h4>
          <ul class="second">
            <li>
              <a href="#Endeavor">Endeavor</a>
            </li>
            <li>
              <a href="#Work">Work</a>
            </li>
            <li>
              <a href="#Expression">Expression</a>
            </li>
            <li>
              <a href="#Manifestation">Manifestation</a>
            </li>
            <li>
              <a href="#Item">Item</a>
            </li>
          </ul>
        </li>
        <li>
          <h4>
            <a href="#properties">Properties</a>
          </h4>
          <ul class="second">
            <li>
              <a href="#responsibleEntity">responsible entity</a>
            </li>
            <li>
              <a href="#relatedWork">related Work</a>
            </li>
            <li>
              <a href="#relatedExpression">related Expression</a>
            </li>
            <li>
              <a href="#relatedManifestation">related Manifestation</a>
            </li>
            <li>
              <a href="#relatedItem">related Item</a>
            </li>
            <li>
              <a href="#expresses">expresses</a>
            </li>
            <li>
              <a href="#expressedBy">expressed by</a>
            </li>
            <li>
              <a href="#manifests">manifests</a>
            </li>
            <li>
              <a href="#manifestedBy">manifested by</a>
            </li>
            <li>
              <a href="#instantiates">instantiates</a>
            </li>
            <li>
              <a href="#instantiatedBy">instantiated by</a>
            </li>
            <li>
              <a href="#commonEndeavor">common Endeavor</a>
            </li>
            <li>
              <a href="#commonWork">common Work</a>
            </li>
            <li>
              <a href="#commonExpression">common Expression</a>
            </li>
            <li>
              <a href="#commonManifestation">common Manifestation</a>
            </li>
            <li>
              <a href="#commonItem">common Item</a>
            </li>
          </ul>
        </li>
        <li>
          <h4>
            <a href="#namespaces">Namespaces</a>
          </h4>
          <ul class="second">
            <li>
              <a href="#dct">dct</a>
            </li>
            <li>
              <a href="#openwemi">openwemi</a>
            </li>
            <li>
              <a href="#owl">owl</a>
            </li>
            <li>
              <a href="#rdf">rdf</a>
            </li>
            <li>
              <a href="#rdfs">rdfs</a>
            </li>
            <li>
              <a href="#skos">skos</a>
            </li>
          </ul>
        </li>
        <li>
          <h4>
            <a href="#legend">Legend</a>
          </h4>
          <ul class="second"></ul>
        </li>
      </ul>
    </div>
  </body>
</html>