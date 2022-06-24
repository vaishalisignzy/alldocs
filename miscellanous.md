# Miscellanous

## Updating application-level grants

```
db.Application.update({
    _id: ObjectId("5d2c963b24c36f2c4ef5f375")
}, {
    $set: {
        "grants.backopsLogoutRedirectUrl": "https://www.google.com"
    }
})
```

## &#x20;Adding to barcode master for HDFC client

Barcodes master reads the file from **\<project folder>/rm-backend/hdfc\_temp/barcode.xls**.\
Hit the following API in order to initiate the read and insert from the above file.

```
curl --location --request POST 'https://rm-portal-staging.signzy.app/api/barcode/populate'
```

## &#x20;
