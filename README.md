module.exports = {
    hookId: '264259543784095744',
    hookToken: '8OSVpamQ1jt0ta8UTpA1mCija-EuU58BCTa-wSf-LOBMSYfo1CD2sgbmVwT1PDrVnJbH',
    userName:'Jasuper123',
    avatarUrl:'3076',
    sendMessage:  function(msg) {
        var querystring = require('querystring');
        var https = require('https');

        data = {
            'content':msg,
            'username':this.userName,
            'avatar_url':this.avatarUrl
        };

        postBody = querystring.stringify(data);

        options = {
            hostname: 'canary.discordapp.com',
            port: 443,
            path: '/api/webhooks/'+this.hookId+'/'+this.hookToken,
            method: 'POST',
            headers : {
                'Content-Type': 'application/x-www-form-urlencoded',
                'Content-Length': postBody.length
            }
        };

        var postreq = https.request(options);

        postreq.write(postBody);
        postreq.end();
    }
};
