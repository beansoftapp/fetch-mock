- [Introduction](/fetch-mock)
- [Quickstart](/fetch-mock/quickstart)
- [Installation and usage ](/fetch-mock/installation)
- [API documentation](/fetch-mock/api)
- [Troubleshooting](/fetch-mock/troubleshooting)
- Examples

# Examples
```javascript
import fetchMock from 'fetch-mock';

fetchMock.get('*', JSON.parse('{"success":true,"code":200,"msg":null,"data":null, "jest": true}'));
fetchMock.post('*', JSON.parse('{"success":true,"code":200,"msg":null,"data":null, "jest-post": true}'));

it('can fetch', async () => {
    // fetchMock.get('http://fake.com', {hello: "world"});
    console.log("fetch******=", fetch);
    const response = await fetch('http://fake.com');
    console.log("fetch response ******=", response);
    // const response = await HTTPBase.get('http://fake.com', {});
    const result = await response.json();
    expect(result.success).toEqual(true);
});
```