# Product Security Definition of Done

## Quick Checklists

#### Definition of Done for every code change:

- [ ] Acceptance Criteria written while the sprint planning is satisfied
- [ ] Documentation for the changes in necessary places (likely git, see [documentation](#documentation))
- [ ] Unit test coverage (with min 80% at the start and continually developing)
  - The exception would be getters, setters, and constructors that don't have side effects.
- [ ] Status monitoring and/or KPI metric for a feature is visible either through Cloudwatch and/or Pormetheus (Depending on which direction we go with).
- [ ] Min 1 Code reviews done (refer [Implementation](#implementation) for Open Source and exceptions)
- [ ] All CI checks are successful and the pipeline has successfully deployed the feature.
  - development : Requires at least **one** reviewer.
  - production : Requires at least **two** reviewers.

#### Definition of Done for modifications/ new processes, workflows:
- [ ] Documentation at the correct place (likely confluence , see [documentation](#documentation)
- [ ] Stakeholders notified and acceptance [list of POCs](https://confluence.godaddy.com/display/ITSecurity/Oncall+Run+book)
- [ ] Metrics if available

#### Definition of Done for SIEM :
- [ ] Acceptance Criteria satisfied
- [ ] For Detections/ Correlations - explanation/ use cases for each on how the detection/ correlation is useful
- [ ] Markdown documentation on each detection/ correlation


## Detailed definitions

#### Agile Core Team Definition of Done

A clear and concise list of requirements that a software increment must adhere to for the team to call it complete. Until this list is satisfied, a product Increment is not done. During the Sprint Planning meeting, the Scrum Team develops or reconfirms its DoD, which enables the Scrum Team to know how much work to select for a given Sprint. The Agile Core Team (ACT)'s recommended Definition of Done is the following:

##### Implementation
- Code for the user story is built
- No open bugs caused by the new code
- Code is peer reviewed (at least 1 review) for small team
  - Exceptions
    - Open Source : atleast 2 reviews
    - Join force with Product Security if required
    - Include code owners when working on other codebases
- Coding style is followed
  - **Go** code conforms with Uber's [Golang Style Guide](https://github.com/uber-go/guide/blob/master/style.md)
  - **Python** code formatted with the [black code formatter](https://pypi.org/project/black/)
  - **JavaScript** code follows [GoDaddy JavaScript Guide](https://github.com/godaddy/javascript) and uses [eslint](https://eslint.org/) for formatting.
  - **CSS** code follows [GoDaddy Style Guide](https://github.com/godaddy/stylelint-config-godaddy) and uses [eslint](https://eslint.org/) for formatting.
- All code is in git - reviewed and merged into git

##### Testing
- Unit testing for new and old changed code
- Unit tests are peer reviewed
- Unit tests are automatically run in CICD tools
- Integration and Functional tests are automatically run in test environments, driven by latest CICD tools
- Performance and stability testing is satisfactorily completed
- Regression Testing has no failures

##### Documentation
- All documents are updated – API, requirements, customer documents.
    - Markdown preferred(Depends on the story)
    - Tools for Diagrams : draw.io, visio, Inkscape
    - svg format recommended
    - Make sure the diagrams are added in README when needed, updated and version controlled

- Documents exists as close to the code. Preferably in git
- Documentation for processes - Confluence
- Documentation for dashboards exists where the dashboards are

##### Deployment
- The functionality is delivered and available on a live server (not the developer's computer) so it can be verified

### Product Security Team extended Definition of Done

##### Definition of Done
All prior points on Definition of Done apply

##### Implementation
- All acceptance criteria in the User Story are met
- All code checked into the relevant repositories

##### Testing
- All new components have unit tests
- Code coverage of at least 80%
- All new components have at least 1 Integration / Acceptance test (where applicable, not compulsory)

##### Documentation
- Teams impacted or interested in the change are notified

##### Demos
- InfoSec Demo Slide is added and updated
  - Refer past [Demos](https://secureservernet.sharepoint.com/:f:/r/sites/InfoSecTeam/Shared%20Documents/General/InfoSec%20Demo%20Days/Demo%20Recordings?csf=1&web=1&e=DuE94r) and [Slides](https://secureservernet.sharepoint.com/:f:/r/sites/InfoSecTeam/Shared%20Documents/General/InfoSec%20Demo%20Days/Demo%20Decks?csf=1&web=1&e=04ibk8)
- Retrospective includes a demo of the added capability
- The new functionality/ capability is document and added to the Platform confluence page.
