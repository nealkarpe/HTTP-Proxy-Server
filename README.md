### Directory Structure
- server directory
  - Contains a server which understands simple GET requests and serves the files from it's directory.
- proxyserver directory
  - The proxy server allows caching of upto 3 files.
  - For a file request, if server's HTTP response contains 'cache-control: must-revalidate' as a header, then for a subsequent request for the same file, the proxy server uses the 'If-Modified-Since' header to check if the file has been changed in the server.
  - Takes care of all error codes.

### Running Instructions
- Start the server using `python server.py`
- Start the proxy server using `python proxy_server.py`
- From terminal, run `curl -x http://localhost:12345 http://localhost:20000/<filename>`
