## ADD THIS SCRIPT TO YOUR WIFIDOG CONFIGURATION

# /etc/wifidog.conf
# if you are using a dns, replace the Hostname to your prefered address where your application is.
# EX: Hostname myauthserver.com
# EX: Hostname myhostname


GatewayID 1234567890
ExternalInterface eth0
GatewayInterface br-lan
AuthServer {
Hostname 10.0.0.11
HTTPPort 80
SSLAvailable no
Path /
}
HTTPDMaxConn 253
ClientTimeout 10
PopularServers kernel.org,ieee.org,cloudwifizone.com,ask.com
FirewallRuleSet global {
#FirewallRule allow to 9.9.9.9
}
FirewallRuleSet validating-users {
FirewallRule allow to 0.0.0.0/0
}
FirewallRuleSet known-users {
FirewallRule allow to 0.0.0.0/0
}
FirewallRuleSet unknown-users {
FirewallRule allow udp port 53
FirewallRule allow tcp port 53
FirewallRule allow udp port 67
FirewallRule allow tcp port 67
FirewallRule block udp port 8000
}
FirewallRuleSet locked-users {
FirewallRule block to 0.0.0.0/0
}

#TrustedMACList 00:00:DE:AD:BE:AF,00:00:C0:1D:F0:0D
