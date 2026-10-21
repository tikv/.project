# TiKV `.project`

`.project` (dot-project) is a CNCF initiative to centralize and automate metadata management for all CNCF projects.
This repository holds the canonical metadata for [TiKV](https://tikv.org) and is maintained by the CNCF automation tooling.

## What's in this repo

| File | Purpose |
|------|---------|
| `project.yaml` | Canonical project metadata (name, maturity, repositories, governance links, …) |
| `maintainers.yaml` | Maintainer and reviewer roster used for drift detection and mailing-list sync |
| `ADOPTERS.md` | Documented TiKV adoption examples and the official adopters list |
| `CODEOWNERS` | Ensures PRs to this repo require maintainer approval |
| `.github/workflows/validate.yaml` | CI — validates `project.yaml` and `maintainers.yaml` on every PR |
| `.github/workflows/update-landscape.yml` | Automatically proposes landscape updates when `project.yaml` changes |

## Keeping metadata up to date

Open a pull request against this repository to update any metadata field.
The validate workflow will check schema correctness and block merge if validation fails.

## Metadata sources

- The [TiKV README](https://github.com/tikv/tikv/blob/master/README.md) identifies
  the primary repository and the TiKV Slack workspace's `#general` channel.
- CNCF announced TiKV's [Sandbox acceptance on August 28, 2018](https://www.cncf.io/blog/2018/08/28/cncf-to-host-tikv-in-the-sandbox/),
  [incubation on May 21, 2019](https://www.cncf.io/blog/2019/05/21/toc-votes-to-move-tikv-into-cncf-incubator/),
  and [graduation on September 2, 2020](https://www.cncf.io/announcements/2020/09/02/cloud-native-computing-foundation-announces-tikv-graduation/).
- The [Docker Compose guide](https://github.com/tikv/tikv/blob/master/docker-compose.README.md)
  uses the [`pingcap/tikv` image](https://hub.docker.com/r/pingcap/tikv).
- The [contribution guide](https://github.com/tikv/tikv/blob/master/CONTRIBUTING.md)
  specifies the Developer Certificate of Origin (DCO).
- The [CNCF maintainer roster](https://github.com/cncf/foundation/blob/main/project-maintainers.csv)
  supplies the existing CNCF contacts. TiKV's [governance document](https://github.com/tikv/community/blob/master/GOVERNANCE.md)
  supplies their current GitHub handles and defines project and team roles.
  `project_lead` retains Siddon Tang as the primary CNCF contact; it does not
  replace the steering committee's governance role.

## Maintainer LFID onboarding

Each maintainer listed in `maintainers.yaml` must:

1. Create or sign in to their Linux Foundation ID (LFID) at
   [openprofile.dev](https://openprofile.dev/).
2. Link the GitHub account listed in `maintainers.yaml` to that LFID.
3. Confirm that their primary email address and company affiliation are current.

These steps require each maintainer's own account access. The YAML schema records
GitHub handles and team membership, not LFIDs, email addresses, or affiliations.
Passing schema validation does not confirm that these account steps are complete.
The validation workflow currently disables LFX account verification pending an
upstream LFX issue, so maintainers must confirm completion in the
[onboarding issue](https://github.com/tikv/.project/issues/1) before it is closed.

## Resources

- [`.project` documentation](https://github.com/cncf/automation/tree/main/utilities/dot-project)
- [Schema reference](https://github.com/cncf/automation/blob/main/utilities/dot-project/SCHEMA.md)
- [CNCF Automation repository](https://github.com/cncf/automation)
