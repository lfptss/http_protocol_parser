# Scripts Overview

## Execution Sequence

### HTTP Request

- `http_parser_clientside.irul`
    - collect tcp payload
    - parse and store the fields in the request header
- `functionRule.irul`
    - implement the function of the HTTP request phase
- `tcp_release_clientside.irul`
    - refresh the variable
    - release and forward the collected payload

### HTTP Response

- `http_parser_serverside.irul`
    - collect tcp payload
    - parse and store the fields in the response header
- `functionRule.irul`
    - implement the function of the HTTP response phase
- `tcp_release_serverside.irul`
    - refresh the variable
    - release and forward the collected payload

## How to test the scripts

- Make the relevant configurations according to the document [how-to-configure](how-to-configure.md)
- Use the iRule statement that prints logs to print the variables you want to check
    1. for example , you want to check http request field **uri**
    2. in the irule **http_parser_clientside.irul** , we have pre-defined the field variables that need to be parsed
    
        ```tcl
        set REQUEST_LINE            ""
        set REQUEST_HEADER          [list]
        set REQUEST_BODY            ""

        set HTTP_METHOD             ""     
        set URI                     ""
        set CLIENT_VERSION          ""

        array set REQ_HEADER_MAP    {}
        set REQ_FIELD_OFFSET_LIST   [list]
        ```
    3. print the log

        `log local0. "uri: $URI"`
    4. use bash command to check the log file
        
        `tail -f /var/log/ltm`
