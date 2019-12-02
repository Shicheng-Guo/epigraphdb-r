# EpiGraphDB R package `epigraphdb`

<a href="http://epigraphdb.org"><img src="man/figures/logo_wide.png" alt="" height="60" style="padding:10px"/></a> <span class="pull-right"> <a href="http://www.bris.ac.uk"><img src="man/figures/ieu40.png" alt="" height="60" style="padding:10px"/></a> <a href="http://www.bris.ac.uk/ieu"><img src="man/figures/uob40.png" alt="" height="60" style="padding:10px"/></a> </span>

<!-- badges: start -->

[![CRAN status](https://www.r-pkg.org/badges/version/epigraphdb)](https://cran.r-project.org/package=epigraphdb)
[![Travis build status](https://travis-ci.org/MRCIEU/epigraphdb-r.svg?branch=master)](https://travis-ci.org/MRCIEU/epigraphdb-r)
[![Codecov test coverage](https://codecov.io/gh/MRCIEU/epigraphdb-r/branch/master/graph/badge.svg)](https://codecov.io/gh/MRCIEU/epigraphdb-r?branch=master)

<!-- badges: end -->

[EpiGraphDB](http://epigraphdb.org) is an analytical platform and database to support data mining in epidemiology. The platform incorporates a graph of causal estimates generated by systematically applying Mendelian randomization to a wide array of phenotypes, and augments this with a wealth of additional data from other bioinformatic sources.
EpiGraphDB aims to support appropriate application and interpretation of causal inference in systematic automated analyses of many phenotypes.

[`epigraphdb`](https://github.com/MRCIEU/epigraphdb-r) is an R package to provide ease of access to EpiGraphDB services. We will refer to `epigraphdb` as the name of the R package whereas `"EpiGraphDB"` as the overall platform.

## Installation

[`devtools`](http://devtools.r-lib.org/)
is required to install from github:

```r
# install.packages("devtools")
devtools::install_github("MRCIEU/epigraphdb-r")
```

**NOTE**: while the package repository is "epigraphdb-r",
the R package name is "epigraphdb".

## Using `epigraphdb`

```r
library("epigraphdb")
#>   EpiGraphDB v0.2
#>
#>   Web API: http://api.epigraphdb.org
#>
#>   To turn off this message, use
#>   suppressPackageStartupMessages({library("epigraphdb")})
mr(outcome = "Body mass index")
#> # A tibble: 370 x 12
#>    exposure_id exposure_name outcome_id outcome_name estimate      se
#>    <chr>       <chr>         <chr>      <chr>           <dbl>   <dbl>
#>  1 627         Epiandroster… 785        Body mass i…   0.0950 2.28e-3
#>  2 541         X-11787       835        Body mass i…  -0.0578 1.77e-4
#>  3 971         Ulcerative c… 835        Body mass i…  -0.0111 1.76e-4
#>  4 60          Waist circum… 835        Body mass i…   0.861  2.07e-2
#>  5 UKB-a:426   Eye problems… 94         Body mass i…  -1.12   1.90e-2
#>  6 UKB-a:373   Ever depress… 95         Body mass i…  -0.616  4.80e-4
#>  7 29          Birth length  95         Body mass i…  -0.141  5.67e-4
#>  8 350         Laurate (12:… 974        Body mass i…   0.418  7.10e-3
#>  9 UKB-a:124   Treatment/me… 974        Body mass i…  -5.14   1.08e-1
#> 10 95          Body mass in… 974        Body mass i…   0.981  2.79e-2
#> # … with 360 more rows, and 6 more variables: p <dbl>, ci_upp <dbl>,
#> #   ci_low <dbl>, selection <chr>, method <chr>, moescore <dbl>)
```

## Functionalities

Below is a list of functionalities that are supported by the `epigraphdb` package.
Advanced users are **encouraged** to use the [API service](http://api.epigraphdb.org) directly.

<table class="table">
  <thead>
    <tr class="header">
      <th><a href="http://api.epigraphdb.org/">API</a></th>
      <th><a href="https://github.com/MRCIEU/epigraphdb-r">r package</a></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Topic queries</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/topics/get_mr_mr_get"><code>GET /mr</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/mr.html"><code>mr</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/topics/get_ontology_ontology_get"><code>GET /ontology</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/ontology.html"><code>ontology</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/topics/get_obs_cor_obs_cor_get"><code>GET /obs_cor</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/obs_cor.html"><code>obs_cor</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/topics/get_gwas_cor_gwas_cor_get"><code>GET /gwas_cor</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/gwas_cor.html"><code>gwas_cor</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/pqtl/get_pqtl_pqtl__get"><code>GET /pqtl/</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/pqtl.html"><code>pqtl</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/pqtl/get_pleio_pqtl_pleio__get"><code>GET /pqtl/pleio/</code></a>
      </td>
      <td>
        <a
          href="https://mrcieu.github.io/epigraphdb-r/reference/pqtl_pleio.html"><code>pqtl_pleio</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/pqtl/get_pqtl_list_pqtl_list__get"><code>GET /pqtl/list</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/pqtl_list.html"><code>pqtl_list</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/topics/get_confounder_confounder_get"><code>GET /confounder</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/confounder.html"><code>confounder</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/topics/get_confounder_pathway_get"><code>GET /pathway</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/pathway.html"><code>pathway</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/drugs/get_drug_risk_factors_drugs_risk-factors_get"><code>GET /drugs/risk-factors</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/drugs_risk_factors.html"><code>drugs_risk_factors</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/xqtl/get_xqtl_multi_snp_mr_xqtl_multi-snp-mr_get"><code>GET /xqtl/multi-snp-mr</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/xqtl_multi_snp_mr.html"><code>xqtl_multi_snp_mr</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/xqtl/get_xqtl_single_snp_mr_xqtl_single-snp-mr_get"><code>GET /xqtl/single-snp-mr</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/xqtl_single_snp_mr.html"><code>xqtl_single_snp_mr</code></a>
      </td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/literature/get_literature_mr_literature_mr_get"><code>GET /literature/mr</code></a>
      </td>
      <td>
        <a href="https://mrcieu.github.io/epigraphdb-r/reference/literature_mr.html"><code>literature_mr</code></a>
      </td>
    </tr>
    <tr>
      <td><strong>Metadata</strong></td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/metadata/get_schema_metadata_schema_get"><code>GET /meta/schema</code></a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/metagraph/meta_nodes_list_meta_nodes_list_get"><code>GET /meta/nodes/list</code></a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/metagraph/nodes_list_meta_nodes__meta_node__list_get"><code>GET /meta/nodes/{meta_node}/list</code></a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/metagraph/nodes_list_names_meta_nodes__meta_node__list-names_get"><code>GET /meta/nodes/{meta_node}/list-names</code></a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/metagraph/nodes_search_meta_nodes__meta_node__search_get"><code>GET /meta/nodes/{meta_node}/search</code></a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/metagraph/nodes_search_neighbour_meta_nodes__meta_node__search-neighbour_get"><code>GET /meta/nodes/{meta_node}/search-neighbour</code></a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/metagraph/meta_rels_list_meta_rels_list_get"><code>GET /meta/rels/list</code></a>
      </td>
      <td></td>
    </tr>
    <tr>
      <td>
        <a href="http://api.epigraphdb.org/#/metagraph/rels_list_meta_rels__meta_rel__list_get"><code>GET /meta/rels/{meta_rel}/list</code></a>
      </td>
      <td></td>
    </tr>
  </tbody>
</table>

## EpiGraphDB resources

| link                                                | screenshot                                            |
|-----------------------------------------------------|-------------------------------------------------------|
| [docs](http://docs.epigraphdb.org)                  | ![docs](vignettes/figures/epigraphdb-docs.png)        |
| [API](http://api.epigraphdb.org)                    | ![api](vignettes/figures/epigraphdb-api-swagger.png)  |
| [web application](http://epigraphdb.org)            | ![webapp](vignettes/figures/epigraphdb-xqtl-view.png) |
| [r package](https://github.com/MRCIEU/epigraphdb-r) | ![epigraphdb-r](vignettes/figures/epigraphdb-r.png)   |

## Citation

If Using EpiGraphDB or the `epigraphdb` R package:

[Elsworth B, Liu Y, Haberland V, Erola P, Lyon M, Zheng J, Gaunt TR. EpiGraphDB. http://epigraphdb.org](http://epigraphdb.org)