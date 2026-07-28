# Projects

This is a showcase of my cybersecurity projects and code I've created.

## Virtual SOC in Azure

### SOC Setup

*   Signed up for an Azure free trial with $200 in free credits.
*   Created a honeypot Standard D2lds v6 (2 vcpus, 4 GiB memory) virtual machine running Windows 11 and port 3389 open.
*   Configured Microsoft Sentinel in a log analytics workspace with Windows Security Events via AMA as my Data Connector.
*   Created detection rules in Sentinel with KQL to detect event 4625 (Attempted RDP sign in) and event 4624 (Successful RDP sign in) and generate incidents

![TestVMCreation](Project_Photos/TestVM_Creation.png)
![DetectionRules](Project_Photos/Detection_Rules.png)
![IncidentGeneration](Project_Photos/Incident_Generation.png)

### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Heatmap](Project_Photos/Heatmap_Workbook.png)

### Large image

![Branching](https://github.com/J0sh0523/J0sh0523.github.io/blob/main/Project%20Photos/Heatmap%20Workbook.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
