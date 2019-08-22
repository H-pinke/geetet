# geetet
This is a sliding verification code

## A api Example

```php
<?php
namespace demo
{
    public partial class GetCaptcha : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            Response.ContentType = "application/json";
            Response.Write(getCaptcha());
            Response.End();
        }
        private String getCaptcha()
        {
            GeetestLib geetest = new GeetestLib(GeetestConfig.publicKey, GeetestConfig.privateKey);
            String userID = "test";
            Byte gtServerStatus = geetest.preProcess(userID,"web","127.0.0.1");
            Session[GeetestLib.gtServerStatusSessionKey] = gtServerStatus;
            Session["userID"] = userID;
            return geetest.getResponseStr();
        }
    }
}
```

```json
"yaohua/geetet": "~1.0"
```

or run

```sh
composer require yaohua/geetet
```

## The official address
https://docs.geetest.com/install/deploy/server/csharp

