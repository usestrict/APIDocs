{{{
  "title": "API Overview",
  "date": "12-19-2014",
  "author": "jw@tier3.com",
  "attachments": []
}}}

## Summary

Tier3 has developed an API exposing most of the same functionality as its Control system (https://control.tier3.com). The API supports REST based HTTP requests using either XML or JSON, as well as SOAP based web services.

The calling conventions for the REST API is to send a POST request to the URL of the given method (e.g. <code>https://api.tier3.com/rest/VirtualServer/CreateServer/<strong>FORMAT</strong></code>, where&nbsp;<strong>FORMAT</strong>&nbsp;is either XML or JSON). In addition, the content type of the HTTP request must be set as well to either "text/xml" for XML requests, or "application/json; charset=utf-8" for JSON requests. The combination of the format node and the Content Type will determine how the request is interpreted as well as control what format the responses are returned.

The SOAP based API supports the same features as the REST API, and while the request and response messages are essentially identical to those of the REST API, you will want to pull down the WSDL for each API to verify the details. URL's to each API's SOAP WSDL can be found on the individual API pages.

All requests will receive a response (in either JSON or XML format) with at least the following three attributes:

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Success</td>
      <td>Boolean</td>
      <td>True if the request was successful, otherwise False.</td>
    </tr>
    <tr>
      <td>Message</td>
      <td>String</td>
      <td>A description of the result. The contents of this field does not contain any actionable information, it is purely intended to provide a human readable description of the result.</td>
    </tr>
    <tr>
      <td>StatusCode</td>
      <td>Int</td>
      <td>This value will help to identify any errors which were encountered while processing the request. The value of '0' indicates success, all non-zero StatusCodes indicate an error state.</td>
    </tr>
  </tbody>
</table>

Many API calls will also return additional information which will be described in detail.