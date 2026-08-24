# FDO Forum Webpages

This repository hosts the webpages of the FDO Forum (Fair Digital Objects Forum).

The rendered preview can be seen here:
https://fairdo-org.github.io/

The official website is https://fairdo.org

## Community-driven development

This website is community-driven. Content and data are maintained by the community members themselves. To suggest or make changes to the site:

1. Fork this repository.
2. Create a branch in your fork and make the changes there.
3. Open a pull request with a description of your changes.

The maintainers review pull requests and merge them into the `main` branch, after which the site is deployed automatically via GitHub Actions.

## Maintainer 
The website is currently maintained by the GWDG. In case of major changes or open issues, the change requests will be discussed at the Steering Group Meeting.

## Contributing data

Most community data lives in YAML files inside the `data/` folder:

- **`data/members.yaml`** – Members of the FDO Forum. Members can **add themselves** to the list and administrate their data.
- **`data/events.yml`** – Events can be added here, grouped by category (e.g. `Meeting`, `Workshop`, `Conference`).

See the comments at the top of each file for the expected fields.