# Projects

This is a showcase of my cybersecurity projects and code I've created.

* * *
## Virtual SOC in Azure

### Honeypot Setup with Detection

*   Signed up for an Azure free trial with $200 in free credits.
*   Created a D2lds v6 (2 vcpus, 4 GiB memory) virtual machine running Windows 11 and port 3389 open.
![TestVMCreation](Project_Photos/TestVM_Creation.png)

*   Configured Microsoft Sentinel in a log analytics workspace with Windows Security Events via AMA as a Data Connector.
*   Created detection rules in Sentinel with KQL to detect event 4625 (Attempted RDP sign in) and event 4624 (Successful RDP sign in) to generate incidents in Sentinel
![DetectionRules](Project_Photos/Detection_Rules.png)
![IncidentGeneration](Project_Photos/Incident_Generation.png)

### Honeypot Results

*   Created a heatmap to track IPs and locations of attempted RDP connections using KQL to sort events

```Kusto
SecurityEvent
| where EventID == 4625
| where isnotempty(IpAddress) and IpAddress !in ("127.0.0.1", "::1", "-")
| summarize Count = count() by IpAddress
| extend GeoInfo = geo_info_from_ip_address(IpAddress)
| extend Latitude = toreal(GeoInfo.latitude)
| extend Longitude = toreal(GeoInfo.longitude)
| extend Country = tostring(GeoInfo.country)
| where isnotempty(Latitude) and isnotempty(Longitude) and isnotempty(Country)
| where Latitude between (-90.0 .. 90.0) and Longitude between (-180.0 .. 180.0)
| project Latitude, Longitude, Count, Country, IpAddress
| order by Count desc
```

![Heatmap_Workbook](Project_Photos/Heatmap_Workbook.png)

### MISP Threat Intelligence Feed

*   Created a new Linux (Ubuntu 24.04) server and installed Docker
*   
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
