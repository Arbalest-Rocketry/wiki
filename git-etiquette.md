
# Git Etiquette

Git is a powerful tool for version control, and following standard etiquette ensures we unlock its full value. Since **Arbalest Rocketry** focuses on high-power rocketry development, including flight computers, payloads, ground stations, and telemetry systems, we adhere to industry best practices. Below is an overview of the standards we follow at **Arbalest Rocketry**.

---

## General

Each repository corresponds to a product:
- Each **PCB** or **hardware module** (e.g., flight computer or payload controller) is a new product.
- **Software systems** (e.g., telemetry, ground station, or navigation) are treated as individual products with distinct revisions.

---

## Review

- No one can push to `master` (or controlled revision branches); all branches must be merged via a **Merge Request (MR)**.
- All code must be reviewed by another team member before merging.
- Ideally, nothing is merged into any branch without an MR to maintain quality and traceability.

---

## Branching Strategy

Each branch is categorized as a feature, hotfix branch, or a dev branch[^Milu][^cheat].

### Naming Conventions

- `hotfix/[ticket_number?]-[description]`
- `feature/[ticket_number?]-[description]`

The `[ticket_number?]` field is optional and corresponds to any issue or task tracking system we use.

### Main Branches

- **`master`**
	- The primary branch containing the latest stable version of the product.

### Development (`dev`) Branches

Development branches are used for different revisions or applications of a product. Examples include:
- **`flight-computer`**
	- Code for rocket avionics and control systems.
- **`payload`**
	- Code for payload experiments, data collection, and management.
- **`groundstation`**
	- Code for base station communication, mission monitoring, and commands.
- **`telemetry`**
	- Code for real-time rocket data logging and transmission.
- **`navigation`**
	- Code for trajectory planning and GPS-based navigation.

---

## Commit Messages

Use descriptive tags such as the following at the start of your commit to make it easily identifiable[^cc]:
- `feat:` – Introduces a new feature.
- `fix:` – Fixes a bug or issue.
- `BREAKING CHANGE:` – Introduces a change that affects backward compatibility.

### Guidelines

- **Start with an imperative verb**:
	- **fix**, not fixing or fixed.
	- **implement**, not implemented or implementing.
- Use the description section to include details of your changes and reasoning[^libscp].
- **Explain why you changed something**, not what you changed—Git already tracks that.

#### Examples

Use the description section to show tests passing and complete details of your changes[^libscp]. Don’t say what you changed—git already shows that—but instead say why you changed it. 
- don’t say: add macro for i2c address
	- This is in the diff, you haven't said anything new
- do say: support bno055 and bmp280 on the same i2c bus
	- This explains your reason

---

## MR Requirements

- All **MRs must pass tests** (automated or manual) before merging.
- Each MR must include a description outlining the purpose of the changes, their impact, and any testing performed.

---

## References
[^Milu]: [Basic Etiquette](https://dev.to/milu_franz/git-explained-proper-team-etiquette-1od)

[^cc]: [How to write commit messages](https://www.conventionalcommits.org/en/v1.0.0/)

[^libscp]: [Examples of good commit messages](https://github.com/libcsp/libcsp/blob/develop/doc/git-commit.md)

[^cheat]: [Reasonable Cheatsheet](https://medium.com/@abhay.pixolo/naming-conventions-for-git-branches-a-cheatsheet-8549feca2534)