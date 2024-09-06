**Domain-driven design** (**DDD**) is a major software design approach, focusing on modeling software to match a [domain](https://en.wikipedia.org/wiki/Domain_(software_engineering) "Domain (software engineering)") according to input from that domain's experts.

Under domain-driven design, the structure and language of software code (class names, [class methods](https://en.wikipedia.org/wiki/Class_method "Class method"), [class variables](https://en.wikipedia.org/wiki/Class_variable "Class variable")) should match the business domain. For example: if software processes loan applications, it might have classes like "loan application", "customers", and methods such as "accept offer" and "withdraw".

Domain-driven design is predicated on the following goals:

- placing the project's primary focus on the core [domain](https://en.wikipedia.org/wiki/Domain_(software_engineering) "Domain (software engineering)") and domain logic;
- basing complex designs on a model of the domain;
- initiating a creative collaboration between technical and [domain experts](https://en.wikipedia.org/wiki/Domain_expert "Domain expert") to iteratively refine a conceptual model that addresses particular domain problems.

Critics of domain-driven design argue that developers must typically implement a great deal of isolation and encapsulation to maintain the model as a pure and helpful construct. 

**While domain-driven design provides benefits such as maintainability, Microsoft recommends it only for complex domains where the model provides clear benefits in formulating a common understanding of the domain**.



Core domain on HR is the employee
Subdomains or helper domains are those who feed or help the core

Problem space vs solution space
![[Pasted image 20231103162011.png]]

#### Problem space
General View about the complexity of the Domain, where to define subdomains
#### Solution space
Model of the solution of the Domain, defining the bounded contexts


#### Bounded context
An explicit boundary within which a domain model exists. Inside the boundarry all terms and phrases of the Ubiquitous Language have specific meaning, and the model reflects the Language with exactness.

The context determines where we are working.

#### Context Mapping
View the different relations between contexts.

Default relations on context mapping include:
- Partnership
- Shared Kernel
- Custormer-supplier development
- Conformist
- Anticorruption-layer (ACL)
- Open host service
- Published language
- Separate ways
- Big Ball of Mud
[Examples](https://github.com/ddd-crew/context-mapping)
