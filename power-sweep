function Test-IPRange {
    param (
        [string]$startIP,
        [string]$endIP
    )
    
    $ipArray = 1..254 | ForEach-Object { "$startIP.$_" }
    
    foreach ($ip in $ipArray) {
        $pingResult = Test-Connection -ComputerName $ip -Count 1 -ErrorAction SilentlyContinue
        if ($pingResult -and $pingResult.StatusCode -eq 0) {
            Write-Host "$ip is reachable."
        } else {
            Write-Host "$ip is not reachable."
        }
    }
}

$startIP = "192.168.1"
$endIP = "192.168.1"

Test-IPRange -startIP $startIP -endIP $endIP
