# terraform-azure-securestorage
Secure Storage module


What is DNS ?

Domain Name System or DNS , translate human readable domains names (for example www.google.com ) to machine readable 

 

What is Azure DNS ? 
Azure DNS is a hosting service for DNS domains that provides name resolution by using Microsoft Azure infrastructure. By hosting your domains in Azure, you can manage your DNS records by using the same credentials, APIs, tools, and billing as your other Azure services.
Azure DNS is based on Azure Resource Manager, which provides features such as:
•	Azure role-based access control (Azure RBAC) to control who has access to specific actions for your organization.

•	Activity logs to monitor how a user in your organization modified a resource or to find an error when troubleshooting.
•	Resource locking to lock a subscription, resource group, or resource. Locking prevents other users in your organization from accidentally deleting or modifying critical resources.


DNS zones
A DNS zone is used to host the DNS records for a particular domain. To start hosting your domain in Azure DNS, we need to create a DNS zone for that domain name. Each DNS record for your domain is then created inside this DNS zone.


 


What is Record Set 

Record Sets: Within a DNS zone, we  can create different types of record sets. 
A record set is a container for DNS records of the same type (e.g., A records, CNAME records) that share the same DNS name (e.g., "www" or "mail"). 

Here are some of the most common types of DNS records:

1. **A (Address) Record:** This record maps a hostname to an IPv4 address. For example, it associates a domain name like "www.example.com" with the corresponding IPv4 address, such as "192.168.1.1."

2. **AAAA (IPv6 Address) Record:** Similar to the A record, but it maps a hostname to an IPv6 address. IPv6 addresses are longer and are used to support the increasing number of devices connected to the internet.

3. **CNAME (Canonical Name) Record:** A CNAME record is used to create an alias for an existing A or AAAA record. It allows multiple domain names to resolve to the same IP address. For instance, "www.example.com" can be a CNAME for "webserver.example.com."

4. **MX (Mail Exchange) Record:** MX records specify the mail servers responsible for receiving email messages for a domain. They include a priority value to determine the order in which email should be routed to multiple mail servers.

5. **TXT (Text) Record:** TXT records can store human-readable text and are often used for purposes like verifying domain ownership, setting up email authentication (SPF and DKIM), or providing general information associated with a domain.

6. **NS (Name Server) Record:** NS records specify the authoritative name servers for a domain. They identify the servers that hold DNS information for a specific domain.

7. **SOA (Start of Authority) Record:** The SOA record contains essential information about the zone, including the primary authoritative name server, the responsible person's email address, and various timing parameters that control DNS record caching and refresh intervals.

8. **PTR (Pointer) Record:** PTR records are used in reverse DNS lookups. They map an IP address to a hostname, enabling the resolution of IP addresses to domain names.


Child DNS zone

In the context of Azure DNS, a "Child DNS Zone" is a type of DNS zone that is subordinate to a parent DNS zone. This structure is commonly used for various purposes, such as delegating the management of a subdomain to a different set of administrators or services. 

Here's how Child DNS Zones work in Azure DNS:

1. **Parent DNS Zone:** This is the top-level or primary DNS zone in your DNS hierarchy. It's the domain for which you have control and are managing DNS records. For example, if you own the domain "example.com," "example.com" would be the parent DNS zone.

2. **Child DNS Zone:** A Child DNS Zone is a subdomain of the parent DNS zone. It's a separate DNS zone that can be independently managed and configured, but it is linked to the parent zone. For example, you might create a child DNS zone like "sub.example.com" under the parent "example.com" zone.

Child DNS Zones in Azure DNS can serve several purposes:

- **Delegation:** You can delegate control of a subdomain to a different set of administrators or services. This allows them to manage their own DNS records within that subdomain. For example, you might delegate control of "sub.example.com" to a different team within your organization.

- **Isolation:** Child DNS Zones can help isolate DNS records and configurations for different purposes or environments. This can be useful for separating development, staging, and production environments, each with its own child DNS zone.

Azure DNS allows you to create, configure, and manage both parent and child DNS zones within the Azure portal. You can define DNS records, configure DNS settings, and specify the name servers for each child zone. This gives you the flexibility to organize your DNS infrastructure efficiently while taking advantage of Azure's DNS hosting and management services.

Azure DNS metrics
Azure DNS provides metrics for you to monitor specific aspects of your DNS zones. With the metrics in Azure DNS, you can configure alerting based on conditions that are met

Azure DNS provides the following metrics to Azure Monitor for your DNS zones:
•	QueryVolume  :- The Query Volume metric shows the number of DNS queries received by Azure DNS for your DNS zone

•	RecordSetCount :- The Record Set Count metric shows the number of Record sets in Azure DNS for your DNS zone.

•	RecordSetCapacityUtilization :- The Record Set Capacity Utilization metric shows the percentage used of your Record set capacity for a DNS Zone

