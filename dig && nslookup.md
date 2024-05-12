The `dig` (Domain Information Groper) and `nslookup` (Name Server Lookup) tools are commonly used for querying DNS servers and are available on most Unix-based systems, including Linux and macOS. Each tool has a variety of flags and options that can be used to tailor the output or specify particular details about the query. Here’s a brief overview of some commonly used flags and options for both:

### dig Command

`dig` is a flexible tool preferred by many network administrators for its robust output and detailed information. Here are some of the commonly used flags and options:

- **+short**: Returns only the answer to the query.
- **+trace**: Provides a trace of the path from the root name servers to the authoritative name servers.
- **+nocmd**: Omits the dig command from the output.
- **+noall**: Turns off all display flags, often used with another option like `+answer` to customize output.
- **+answer**: Displays only the answer section of the response.
- **+stats**: Provides statistics about the operation of `dig`.
- **+noquestion**: Omits the question section from the output.
- **+nocomments**: Eliminates comments in the output, making it easier to read or parse programmatically.
- **+tcp**: Uses TCP instead of UDP to perform the query, useful for larger responses that exceed UDP limits.
- **-t TYPE**: Specifies the type of query (e.g., A, MX, TXT).

Example:
```bash
dig example.com +noall +answer
```

### nslookup Command

`nslookup` is another tool used for DNS querying but is considered less robust than `dig`. It's still very useful, especially on systems where `dig` might not be available. Here are some flags and options for `nslookup`:

- **-type=TYPE**: Sets the query type (e.g., A, MX, NS).
- **-debug**: Shows the full response from the DNS server, including debugging information.
- **-query=TYPE or -qt=TYPE**: Same as `-type`, specifies the type of the DNS record to be queried.
- **-port=NUMBER**: Specifies the port number to send the query to (default is 53).
- **-timeout=NUMBER**: Sets the query timeout in seconds.

Example:
```bash
nslookup -type=MX example.com
```

### Usage Notes

- **`dig`** is generally preferred for scripting because of its predictable output format and extensive detail.
- **`nslookup`** is often used interactively and is available by default on many Windows systems as well as Unix-like operating systems.
