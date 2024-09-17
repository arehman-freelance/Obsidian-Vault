# Container DB requirements
- install oracle free db
- install oracle ords
- limit resources
- assign static ips
- use docker compose
- ords with ssl
- install apache on host
- reverse proxy from apache to container ords
- setup apache with ssl

- jmeter test results #todo
![[jmeter testing .pdf]]

# centerlize documentation system
## confluence

- [https://anyquiz.atlassian.net/wiki/spaces/support/pages/66268/Container+DB](https://anyquiz.atlassian.net/wiki/spaces/support/pages/66268/Container+DB)

## obsidian

- [https://obsidian.md/pricing](https://obsidian.md/pricing)

## open source

- [https://www.getoutline.com/](https://www.getoutline.com/)
- [https://js.wiki/](https://js.wiki/)
- [https://www.bookstackapp.com/](https://www.bookstackapp.com/)


# cloud db
installed and licensed database node - 220 USD small (1ocpu, 16gb ram, 512 storage)
repo sources are not available to update
vm backup -> no process
only can take backup on db - rman
backup -> object storage
compute -> ords and apache
also ords machine backup
cost around 300 USD and selling price 360 USD
reduce cost
**use docker for apache and ords**
we can use archive storage to take backup
minified version of **virtualmin** also on docker



# ticket-ai
- ~~need to deploy **ticket-ai** on all prod servers. also increase tomcat logs lines to 100~~
-~~pass multiple replies to chatgpt~~
- ~~update prompt~~

https://dev.maxapex.net/nazim/supporttickets.php?action=viewticket&id=154184

https://dev.maxapex.net/nazim/supporttickets.php?action=viewticket&id=154183

