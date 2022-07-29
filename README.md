# douyin-deviceid-demo
register douyin device id such as did iid for douyin android 


success response
```json
{
    "device_id": "2159776194*****",
    "iid": "218630245633****",
    "uuid": "86126512500*****",
    "openudid": "3448906853****",
    "register_response": "{\"device_token\":\"AAAVHQV7VVKEXBPAY2YQJWYZUDYSFLM52NV7XVBB26SETU434YMPAI6RVYWXTNNOHCDBGJHT5TLACEPHEZ5FTO36EXJZBW2GNPFLZT5I6P7GMAB72CBLHE*****\",\"server_time\":165906****,\"device_id\":2159776194*****,\"install_id\":218630245633****,\"device_id_str\":\"21597761940****\",\"install_id_str\":\"2186302456****\",\"new_user\":1}",
    "verify_response": "{\"message\":\"success\"}"
}


```

failed response
```json
{
    "device_id": "0",
    "iid": "0",
    "uuid": "8612679568*****",
    "openudid": "0700151849848979",
    "register_response": "{\"server_time\":1659066167,\"device_id\":0,\"install_id\":0,\"device_id_str\":\"0\",\"install_id_str\":\"0\",\"new_user\":0}",
    "verify_response": "{\"message\":\"success\"}"
}

```

the web-framework using fastapi.
the api has add random sleep for each request such as:
```python

@app.middleware("http")
async def get_remote_ip(request: Request, call_next):
    rand_int = random.randint(0, 100)
    if rand_int > 10:
        time.sleep(5)
    else:
        random_sleep = random.randint(1, 10)
        time.sleep(random_sleep)
    response = await call_next(request)
    return response

```

If you are interested in this project, leave your contact information in the issue such wechat or telegram
