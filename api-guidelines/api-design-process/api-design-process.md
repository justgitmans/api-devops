## API Modelling and Design Process

The following API Modelling Process has been excerpted from chapter 4 and chapter 6 of [A Practical Approach to API Design](https://leanpub.com/restful-api-design) by D. Keith Casey Jr and James Higginbotham. (**This is just a brief summary for educational purpose - please consider buying the book to support their excellent work**)

### API Modelling Process
API modeling consists of 5 activities that help identify the requirements of your API design:

As you move from the modeling to the design phase, you will be faced with a variety of decisions. Some of these will resolve easily, while others will take time and deliberation. Just know that it is difficult to get your API design right the first time. This is why we encourage you to spend time designing and prototyping your API before you start implementing it.

#### Building Your Resource Taxonomy
To get started building your taxonomy, make a list of the resources you have modeled already. These are often identified as the nouns in your system. Keep in mind that some resources may belong as a child collection of another resource.

#### How to Handle Resource Relationships and Composition
Resources often contain child resources or reference other resources. In these cases, the API design must ensure that one can interact with the top-level resource as well as nested and related resources.

 Independent  | The resources exist stand alone without the other’s existence, but may reference each other        
 Dependent    | One resource cannot exist without the existence of the parent resource
 Associative  | The resources exist independently, however their relationship contains or requires additional properties to describe it



Please see [HTTP Status Codes](../http-status-codes/http-status-codes.md) for a more in depth discussion.

3. Allow clients to explore resource relationships

The following is a quick summary of Hypermedia Linking

* ***Link Thyself***: Every resource should define a link to itself. While this seems to be redundant, or perhaps wasteful, there is a valid reason for returning a link to a returned resource: clients should never have to track the link that returned a resource separate from the resource representation itself.
* ***Resource State Linking***: Look for any constraints and state transitions that a resource may require. These constraints should be surfaced as links, offering insight into what actions are allowed and not allowed given the current state of a resource.
* ***Relationship Linking***: Resources should include links to a parent resource, children, or related resources as identified during the previous taxonomy step.
* ***Additional Navigation Links***: Most commonly used for collection responses, where you may need to offer pagination links for next and previous pages, and for navigation to other areas of the API.

Please see [Hypermedia and Rest](../hypermedia-and-rest/hypermedia-and-rest.md) for a more in depth discussion of Hypermedia.

---

A good reference book for APIs and API Design is the afore mentioned [A Practical Approach to API Design](https://leanpub.com/restful-api-design) by D. Keith Casey Jr and James Higginbotham.