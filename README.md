local url = "https://discordapp.com/api/webhooks/264292569343590403/l1rU-A8zrqDppWIzgrL8r-vBBlvYcNUKI17tFqFTPgYuAn_H7dYhuwexGu8YQEUSLJ_3" -- Put the Webhook URL you copied in this!
local http = game:GetService("HttpService")
local HookData = {
['username'] = "U.S. Judge",
['content'] = "You're all being Judged."
}
HookData = http:JSONEncode(HookData)
http:PostAsync(url, HookData)
