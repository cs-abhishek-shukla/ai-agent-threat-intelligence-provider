# Release Information

- **Version**: 1.0.0

- **Certified**: Yes

- **Publisher**: Fortinet

- **Scope**: Context and Enrichment, Triage

- **Verified with Models**: Fortinet FortiAI (AI model Medium)

# Threat Intelligence Provider

Enriches indicators (IPs, domains, URLs, file hashes, emails, ports) with external and internal threat intelligence, providing reputation scores, threat associations, geolocation data, ASN details, and campaign attribution for threat identification.

## Installation

This agent installs along with the FortiAI solution pack.

## Configuration

**Required MCP Servers**: SOC Framework

> [!Note]
>
> Refer to [Configuring MCP Servers](https://docs.fortinet.com/document/fortisoar/8.0.0/administration-guide/823139/mcp-servers#Configure_MCP_Servers) on FortiSOAR platform documentation for information on configuring a custom MCP server.
> 

### Prerequisites

- The FortiAI solution pack must be installed and configured with the Fortinet FortiAI connector.

  - To configure the FortiAI solution pack, refer to the [FortiAI](https://github.com/fortinet-fortisoar/solution-pack-fortinet-advisor/) solution pack documentation.
  - To configure the Fortinet FortiAI connector, refer to the [Fortinet FortiAI](https://docs.fortinet.com/fortisoar/connectors/fortinet-fortiai) connector documentation.

> [!Note]
>
> FortiAI solution pack and Fortinet FortiAI connector are preconfigured out-of-the-box with FortiSOAR `v8.0.0`.
> 


## Input Parameters

The input must be provided as a JSON object.

| Parameter  | Description                                                                                           |
|------------|-------------------------------------------------------------------------------------------------------|
| `question` | The question that needs to be answered.                                                               |
| `ioc`      | List of IOC (Indicator of Compromise) objects to enrich. Each IOC object must contain value and type. |

### IOC Object Fields

| Field   | Description                                                                                                                                                                |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `value` | The actual indicator data to enrich. Example: IP address (8.8.8.8), domain (example.com), URL (https://example.com/login), email address (user@example.com), or file hash. |
| `type`  | The type/category of the indicator. Supported values are: IP Address, Domain, Email Address, File, FileHash-MD5, FileHash-SHA1, FileHash-SHA256, URL, User.                |

## Response

The output is returned as a JSON object.

| Parameter    | Description                                                     |
|--------------|-----------------------------------------------------------------|
| `answer`     | Answer to the query derived from available data.                |
| `confidence` | Confidence percentage indicating reliability of the answer (For example: *85%*).     |
| `evidence`   | Supporting information and details from retrieved data sources. |

