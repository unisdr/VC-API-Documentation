The API exposes the registration / participants information from the excel exported file report from the Indico system.

## All registraton

This endpoint will retrieve all the raw registration information from Indico in JSON format. The data are read from the uploaded registration excel report from Indico.

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### URL: /sso-unisdr/indico/event/registration/all/{code}

* {code} integer, this is the event ID in Indico
* /sso-unisdr/indico/event/registration/all/1000230

### JSON Response

```shell
{
  "header": [
    {
      "j1": "Select",
      "j2": "Last Name \/ Apellido",
      "j3": "First Name \/ Nombre",
      "j4": "Email",
      "j5": "Status",
      "j6": "Representation Type",
      "j7": "Rep Sub Type",
      "j8": "Registration Date",
      "j9": "A.  I am Head of a Delegation \/ Soy Jefe de una Delegación",
      "j10": "Address \/ Dirección",
      "j11": "B. I represent an institution \/ Representa a una institución",
      "j12": "Badge Type",
      "j13": "Birth Date \/ Fecha de nacimiento",
      "j14": "Check-in Date",
      "j15": "City \/ Ciudad",
      "j16": "Country \/ País",
      "j17": "Event Title",
      "j18": "Gender \/ Género",
      "j19": "I may need some accessibility measures \/ Necesito medidas de accesibilidad",
      "j20": "I understand and consent that all the data collected through this form will be shared with the host country (Jamaica) for security, logistics, and communication purposes \/ Entiendo y acepto que todos los datos recopilados a través de este formulario se compartirán con el país anfitrión (Jamaica) por motivos de seguridad, logística y comunicación",
      "j21": "ID Number \/ Número de Identificación",
      "j22": "regId",
      "j23": "If YES, Indicate your role  \/  En caso afirmativo, informe su cargo",
      "j24": "If YES, name of institution \/ En caso afirmativo, nombre Institución",
      "j25": "Nationality \/ Nacionalidad",
      "j26": "Number of Prints",
      "j27": "Other \/ Otro",
      "j28": "Passport Expire\/Fecha de vencimiento del pasaporte",
      "j29": "Phone \/ Teléfono",
      "j30": "Picture \/ Fotografía",
      "j31": "Please inform the additional requirements you might need \/ Por favor infórmenos del tipo de asistencia adicional que usted pudiese requerir",
      "j32": "Position \/ Posición",
      "j33": "Printed Date",
      "j34": "Rank",
      "j35": "RegistrationForm Title",
      "j36": "Rejection Reason",
      "j37": "RepType Qualifier",
      "j38": "RepType UN Body fullname",
      "j39": "Size of your institution \/ Tamano de la institución",
      "j40": "Tags",
      "j41": "Title \/ Título",
      "j42": "Type of ID \/ Tipo de Identificación",
      "j43": "Type of disability (Optional) \/ Tipo de discapacidad (Opcional)",
      "j44": "Vip",
      "j45": "Watchlisted"
    }
  ],
  "data": [
    {
      "j1": null,
      "j2": "John",
      "j3": "Well",
      "j4": "well@email.com",
      "j5": "Pending",
      "j6": "Academia",
      "j7": "University of Margate",
      "j8": "2021\/09\/14 21:19",
      "j9": "No \/ No",
      "j10": "House, Street 90210",
      "j11": "No \/ No",
      "j12": "Academia",
      "j13": "1970\/01\/01",
      "j14": null,
      "j15": "-",
      "j16": "-",
      "j17": "VII Regional Platform for Disaster Risk Reduction in the Americas and the Caribbean (RP21)",
      "j18": "Male \/ Masculino",
      "j19": "no",
      "j20": "yes",
      "j21": 12345,
      "j22": 67890,
      "j23": null,
      "j24": null,
      "j25": "-",
      "j26": 0,
      "j27": null,
      "j28": "2000\/01\/01",
      "j29": "-",
      "j30": null,
      "j31": null,
      "j32": null,
      "j33": null,
      "j34": 0,
      "j35": "New Registration \/ Nuevo Registro",
      "j36": null,
      "j37": null,
      "j38": null,
      "j39": null,
      "j40": null,
      "j41": "Mr",
      "j42": "Government issued ID \/ Documento de identidad emitido por el Gobierno",
      "j43": null,
      "j44": "no",
      "j45": "no"
    },
	...
  ],
  "other": {
    "total": 100
  }
}
```


## Participants

This endpoint shows all the approved registrations. But since the Excel report column headers are not standard, manual intervention per event is needed to expose the appropriate fields. The example below is based on RP America Indico registration.

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### URL: /sso-unisdr/indico/event/registration/approved/{code}

* {code} integer, this is the event ID in Indico
* /sso-unisdr/indico/event/registration/approved/1000230

### JSON Response

```shell
{
  "header": {
    "j1": "Last Name \/ Apellido",
    "j2": "First Name \/ Nombre",
    "j3": "Email",
    "j4": "Representation Type",
    "j5": "Rep Sub Type",
    "j6": "Registration Date",
    "j7": "Badge Type",
    "j8": "Country \/ País",
    "j9": "Position \/ Posición",
    "j10": "RepType UN Body fullname",
    "j11": "Title \/ Título",
    "j12": "Vip"
  },
  "data": [
    {
      "j1": "Joe",
      "j2": "Well",
      "j3": "joe.well@email.com",
      "j4": "Other",
      "j5": "ABC Inc.",
      "j6": "2021\/01\/01 13:08",
      "j7": "Other",
      "j8": "Thailand",
      "j9": null,
      "j10": null,
      "j11": "Mr",
      "j12": "no"
    },
    ...
  ],
  "other": {
    "total": 149
  }
}    
```



## Upload Excel from Indico

This endpoint is to update the excel file. The process can be done manually or automated.

### Authentication:

oAuth2 client credentials, please refer to other documentation how to get the client access token.

### Header Parameters:

* Accept string, value "application/json"
* Authorization string, value "Bearer [Client: ACCESS TOKEN]"

### Method

* POST

### URL: /sso-unisdr/api/integration/indico/event/registration/upload-report/{code}

* {code} integer, this is the event ID in Indico
* /sso-unisdr/api/integration/indico/event/registration/upload-report/1000230

### JSON Response

```shell
{
  "status": 200,
  "success": 1,
  "message": "File uploaded"
}
```


### Example

#### HTTP
```shell
POST http://[SERVER]/sso-unisdr/api/integration/indico/event/registration/upload-report/1000230 HTTP/1.1
Accept: application/json
Content-Type: multipart/form-data; boundary=---011000010111000001101001
Authorization: Bearer [CLIENT TOKEN]
Host: localhost
Content-Length: 242

-----011000010111000001101001
Content-Disposition: form-data; name="file"; filename="RegistrantsList_export_1000230.xlsx"
Content-Type: application/vnd.openxmlformats-officedocument.spreadsheetml.sheet


-----011000010111000001101001--
```

#### JAVA
```shell
HttpResponse<String> response = Unirest.post("http://[SERVER]/sso-unisdr/api/integration/indico/event/registration/upload-report/1000230")
  .header("Accept", "application/json")
  .header("Content-Type", "multipart/form-data; boundary=---011000010111000001101001")
  .header("Authorization", "Bearer [CLIENT TOKEN]")
  .body("-----011000010111000001101001\r\nContent-Disposition: form-data; name=\"file\"; filename=\"RegistrantsList_export_1000230.xlsx\"\r\nContent-Type: application/vnd.openxmlformats-officedocument.spreadsheetml.sheet\r\n\r\n\r\n-----011000010111000001101001--\r\n")
  .asString();
```


#### PHP
```shell
$curl = curl_init();

curl_setopt_array($curl, [
  CURLOPT_URL => "http://[SERVER]/sso-unisdr/api/integration/indico/event/registration/upload-report/1000230",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => "-----011000010111000001101001\r\nContent-Disposition: form-data; name=\"file\"; filename=\"RegistrantsList_export_1000230.xlsx\"\r\nContent-Type: application/vnd.openxmlformats-officedocument.spreadsheetml.sheet\r\n\r\n\r\n-----011000010111000001101001--\r\n",
  CURLOPT_HTTPHEADER => [
    "Accept: application/json",
    "Authorization: Bearer [CLIENT TOKEN]",
    "Content-Type: multipart/form-data; boundary=---011000010111000001101001"
  ],
]);

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```
