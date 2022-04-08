# lern-python-soap
lerning python soap

## example code

````
import requests
# SOAP request URL
# Simple Object Access Protocol
url = "http://webservices.oorsprong.org/websamples.countryinfo/CountryInfoService.wso"

# structured XML
payload = """<?xml version=\"1.0\" encoding=\"utf-8\"?>
            <soap:Envelope xmlns:soap=\"http://schemas.xmlsoap.org/soap/envelope/\">
                <soap:Body>
                    <CountryIntPhoneCode xmlns=\"http://www.oorsprong.org/websamples.countryinfo\">
                        <sCountryISOCode>IN</sCountryISOCode>
                    </CountryIntPhoneCode>
                </soap:Body>
            </soap:Envelope>"""
# headers
headers = {
    'Content-Type': 'text/xml; charset=utf-8'
}
# POST request
response = requests.request("POST", url, headers=headers, data=payload)

# prints the response
print(response.text)
print(response)
````

## result

````
D:\dev\python\soap>python test-soap.py
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <m:CountryIntPhoneCodeResponse xmlns:m="http://www.oorsprong.org/websamples.countryinfo">
      <m:CountryIntPhoneCodeResult>91</m:CountryIntPhoneCodeResult>
    </m:CountryIntPhoneCodeResponse>
  </soap:Body>
</soap:Envelope>
<Response [200]>

D:\dev\python\soap>
````

