### Kill process on server
```bash
pkill node
```
### Fetch api
```js
  private setCarouselImages() {
    const requestOptions = {
      method: 'GET', // GET/POST
      headers: {
        'Content-Type': 'application/json',
      },
      // body: JSON.stringify({ title: 'Fetch POST Request Example' }) // Uncomment this line for POST method
    };
    fetch(Endpoints.files.list, requestOptions)
      .then(response => response.json())
      .then(data => console.log(data) );
  }
  ```
