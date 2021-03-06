# Sites

Domains and their configuration / origin(s). This documents the MetaCPAN domains and subdomains, and where they are currently hosted.

### Notes:

- LW = Liquid web data center
- BM = Bytemark data center ( primary for Elasticsearch and therefore the API )

## Fastly - CDN

### Primary sites

[https://metacpan.org/](https://metacpan.org/)  ( fastly also take http and converts to httpS )

 * load balanced + health checks: lw-mc-01, lw-mc-02, bm-mc-01, bm-mc-02

[http://fastapi.metacpan.org/](http://fastapi.metacpan.org/)

 * load balanced + health checks: bm-mc-01, bm-mc-02, bm-mc-04  (as need to talk to same Elasticsearch always)

### Other sites

[http://search.cpan.org/](http://search.cpan.org/), [http://search.mcpan.org/](http://search.mcpan.org/), [http://mcpan.org/](http://mcpan.org/) && [http://sco.metacpan.org/](http://sco.metacpan.org/) - redirects

 * load balanced (heavily to LW) + health checks: lw-mc-01, lw-mc-02, lw-mc-03, bm-mc-02, bm-mc-04

[https://cpan.metacpan.org/](https://cpan.metacpan.org/) && [https://backpan.metacpan.org/](https://backpan.metacpan.org/) - and _http_

 * origin: lw-mc-01:80 - 45%, lw-mc-02:80 - 45%, bm-mc-02:80 5% & bm-mc-04:80 5%

[http://explorer.metacpan.org/](http://explorer.metacpan.org/)

 * origin: lw-mc-01

[https://v1.metacpan.org/](https://v1.metacpan.org/)

 * Entirely on fastly, no origin - it just redirects

[http://www.metacpan.org/](http://www.metacpan.org/), [https://www.metacpan.org/](https://www.metacpan.org/) - redirect to [https://metacpan.org/](https://metacpan.org/)

 * Entirely on fastly, no origin

[http://api.metacpan.org/](http://api.metacpan.org/) - v0 of the API

  * bm-mc-01 & lw-mc-02 - running the shim

[http://munin.metacpan.org](http://munin.metacpan.org)

 * lw-mc-01
 
 [http://gh.metacpan.org](http://gh.metacpan.org)
 
 * lw-mc-02
 
 [http://grep.metacpan.org](http://grep.metacpan.org)
 
 * bm-mc-02

