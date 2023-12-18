## Abstract

This document proposes the introduction of a new HTTP status code, "512 Client Not Supported," to be utilized by servers when encountering a client (typically a web browser) that is not supported or compatible with the server's capabilities.

## Motivation

As web technologies evolve, server-side implementations may advance beyond the capabilities of certain clients. To address this, a dedicated HTTP status code is needed to inform clients that their version or type is not supported by the server.

## Status Code: 512

### Title: Client Not Supported

### Description

The server has determined that the client, such as a web browser, is not supported or compatible with its current capabilities. The client should consider upgrading or switching to a supported version to access the requested resource successfully.

### Usage

When a server encounters a client that it cannot adequately support, it should respond with a 512 status code. Alongside the status code, the server may include additional information in the response body, detailing the reasons for the client's lack of support and suggestions for resolution.

### Example

```http
HTTP/1.1 512 Client Not Supported
Content-Type: text/plain

Your web browser is not supported by this server. Please consider upgrading to a more recent version or switch to a supported browser.
```

## Considerations

- Servers should provide clear and informative messages in the response body to guide clients on how to resolve the compatibility issue.
- Clients encountering this error should follow the guidance provided by the server to upgrade or switch to a supported version.

## Security Considerations

Implementations of this status code should be mindful of potential security implications. It is recommended to avoid revealing excessive details about the server's configuration or reasons for lack of support.

## IANA Considerations

**1. Registration Information:**
   
   - **Status Code:** 512
   - **Description:** Client Not Supported
   - **Reference:** This specification serves as the reference for the definition and usage of the "512 Client Not Supported" status code.

**2. Usage Guidance:**

   - The "512 Client Not Supported" status code indicates that the server refuses to process the request because the client lacks capabilities needed for successful processing.
   - Clients receiving this status code should review the server's response headers or documentation to identify the specific requirements or capabilities that are lacking.

**3. Contact:**

   - For inquiries or further information regarding the use of this status code, contact the document authors or the responsible party designated in the HTTP protocol specifications.

**4. Security Considerations:**

   - Implementers and users should be aware that this status code may be employed to enhance security by preventing the execution of requests by inadequately equipped clients.

**5. Interoperability Considerations:**

   - Servers and clients implementing support for this status code should do so in accordance with the specifications outlined in this document to ensure consistent and interoperable behavior across the Internet.

**6. IANA Considerations:**

   - IANA is requested to update the Hypertext Transfer Protocol (HTTP) status code registry by adding the entry for "512 Client Not Supported" as specified in this document.

## Conclusion

The introduction of the "512 Client Not Supported" HTTP status code will enhance the communication between servers and clients, providing a standardized way to handle situations where a client's capabilities are insufficient for the requested resource. This proposal encourages clearer guidance for clients to resolve compatibility issues and ensures a more user-friendly web experience.
