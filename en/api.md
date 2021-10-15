# API usage

## Curl

Request example:

```
curl -i -X POST -H "Content-Type: multipart/form-data" -F "data=@image_2021-08-16_17-44-50.png" https://ftl-aiijc.herokuapp.com/predict
```

## Python

Request example:

```python
import requests

files = {
    'img[]': open('image_2021-08-16_17-44-50.png', 'rb')
}

response = requests.post('https://ftl-aiijc.herokuapp.com/predict', files=files)
print(response.text)
```

## Response format

Server will return json in this format:
```json
{
  "status": "success",
  "lanes": [
    {
      "straight": true,
      "left": true,
      "right": false,
      "slightlyLeft": false,
      "slightlyRight": false,
      "rightThenLeft": false,
    }, {
      "straight": false,
      "left": false,
      "right": false,
      "slightlyLeft": true,
      "slightlyRight": true,
      "rightThenLeft": false,
    }, {
      "straight": true,
      "left": false,
      "right": true,
      "slightlyLeft": false,
      "slightlyRight": false,
      "rightThenLeft": true,
    }
  ]
}
```

Response examples: 


<table>
<tr>
<td> Response </td> <td> Sign </td>
</tr>
<tr>
<td> 

```json
{
  "status": "success",
  "lanes": [
    {
      "straight": true,
      "left": false,
      "right": false,
      "slightlyLeft": false,
      "slightlyRight": false,
      "rightThenLeft": true,
    }
  ]
}
```

 </td>
<td>

<img src="https://i.imgur.com/t91YMqH.png" height="300"/>

</td>
</tr>

<tr>
<td> 

```json
{
  "status": "success",
  "lanes": [
    {
      "straight": false,
      "left": true,
      "right": false,
      "slightlyLeft": false,
      "slightlyRight": false,
      "rightThenLeft": false,
    },
    {
      "straight": false,
      "left": false,
      "right": false,
      "slightlyLeft": false,
      "slightlyRight": true,
      "rightThenLeft": false,
    }
  ]
}
```

 </td>
<td>

<img src="https://i.imgur.com/xJbipPk.png" height="300"/>

</td>
</tr>

<tr>
<td> 

```json
{
  "status": "success",
  "lanes": [
    {
      "straight": true,
      "left": true,
      "right": false,
      "slightlyLeft": false,
      "slightlyRight": false,
      "rightThenLeft": false,
    },
    {
      "straight": true,
      "left": false,
      "right": false,
      "slightlyLeft": false,
      "slightlyRight": false,
      "rightThenLeft": false,
    },
    {
      "straight": false,
      "left": false,
      "right": true,
      "slightlyLeft": false,
      "slightlyRight": false,
      "rightThenLeft": false,
    }
  ]
}
```

 </td>
<td>

<img src="https://i.imgur.com/niCAyhn.png" height="300"/>

</td>
</tr>

</table>