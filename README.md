Getting Started

Set your server info

// Replace with your server IP and port
$firstIp = "iphere";
$firstPort = 23693;

// Another server if you have it
$secondIp = "OPTIONAL SECOND SERVER IP";
$secondPort = 13481;


Use the RCCServiceSoap class

This class handles sending requests and parsing responses for you. You can customize:

IP and Port of the server

URL (your server URL)

Render Fix (fixes messy output from some servers)

$soap = new RCCServiceSoap(
    $ip = "serverip",  // Your server IP
    $port = 64989,            // Your server port
    $url = "",      // Your server URL
    $renderFix = true         // Keep it on, it helps with formatting
);

Sending Scripts

You can run any Lua script easily:

$result = $soap->execScript('print("Hello World!")', 'helloworld', 0.1);
echo $result;


execScript($script, $jobId, $jobExpiration) – runs your Lua script.

helloWorld() – a quick test function to make sure everything works.

How it Works

Builds a SOAP XML request

Sends it to your RCC server

Cleans up the messy output so you just get the result

Tips

Always replace the default IPs and ports with your own servers.

Keep renderFix as true unless you know your server output is already clean.

Use short job expiration times for testing, e.g., 0.1 seconds.
