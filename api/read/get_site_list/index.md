# GOCDB Programmatic Interface - Read

## Method: get_site_list

### Entry point

- `/gocdbpi/public/?method=get_site_list`

### Information

| Description | Protection Level |
| - | - |
| Returns a list of sites with minimal associated information | Public (level 1) |

| Parameters | Effect | Format/Value(s) | Default | Example |
| - | - | - | - | - |
| `sitename` | Only return info for site with specified site name | any site name | `all` | `?method=get_site_list&sitename=RAL-LCG2` |
| `roc` | Limit results to sites belonging to given NGI | any NGI name | `all` | `?method=get_site_list&roc=NGI_DE` |
| `country` | Limit results to sites belonging to given country | any country | `all` | `?method=get_site_list&country=Poland` |
| `certification_status` | Limit results to sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | `all` |  `?method=get_site&certification_status=Certified` |
| `exclude_certification_status` | Exclude from results sites with given certification status | one of `Candidate`, `Uncertified`, `Certified`, `Closed`, `Suspended` | none |  `?method=get_site&exclude_certification_status=Closed` |
| `production_status` | Limit results to sites within given production infrastructure | one of `Production` or `Test` | `all` |  `?method=get_site&production_status=Production` |
| `scope` | Show only sites with the requested scope tags | A comma separated list of scope-tag values or an empty value to return all scopes, i.e. `&scope=` | instance dependant |  `?method=get_site&scope=Local` |
| `scope_match` | Match `all` or `any` of the specified scope-tags | `all` or `any` | `all` |  `?method=get_site_list&scope=Local,EGI&scope_match=any` |
| `extensions` | Limit results by one or many key value pairs | [See Extensions Mechanism](https://docs.egi.eu/internal/configuration-database/extension-properties/) | none |  `?method=get_site&extensions=(KeyName=KeyValue)` |

### Paging

This method does not support paging.

### Output_Example

```xml
<?xml version="1.0" encoding="UTF-8"?>
<results>
  <SITE ID="335" PRIMARY_KEY="123G0" NAME="GRIDOPS-GOCDB" COUNTRY="United Kingdom" COUNTRY_CODE="GB" ROC="EGI.eu" SUBGRID="" GIIS_URL=""/>
</results>
```