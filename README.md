## SFDC Process Builder notes

#### I. How to use Process Builder to provide Opportunity Assignment Rules feature (like Lead and Case Assignment rules)?


Screenshot showing sample Lead Assignment Rule:

``` python
if  Lead.Industry == 'Entertainment' :
	assign_to('this_user')
```

![Lead Assignment Rule](./img/lead-assignment-rule.png)


#### Use case

- Assign the owner for the Opportunity record being created based on this Criteria:

1. Opportunity.Amount            >= $30,000
2. AND Opportunity.Probability   >=  50% 
3. OR Opportunity.Stage == 'Value Proposition'
	
So the logic needed is : **1 AND (2 OR 3)**


**Demo showing the Opportunity Assignment :**

![Oppty Assignment Rule](./img/oppty-routing-2.gif)


- **Post to Chatter page of the user** (to whom this newly created Opportunity is assigned to) about this assignmet:

Example:

```
Opportunity: 800 solar panels with amount: 34,000 in stage:Value Proposition is just routed to you!

```
<hr/>

**Demo showing the chatter post:**

![Oppty Assignment Rule](./img/oppty-routing-with-chatter-post.gif)

### Automation tools comparsion 

![Compare tools 1 ](./img/compare-0.png)
![Compare tools 2 ](./img/compare-1.png)

[Ref](https://trailhead.salesforce.com/modules/business_process_automation/units/process_whichtool)
