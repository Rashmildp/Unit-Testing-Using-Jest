
# Unit test using JEST

### Test API calls 

Not using mocking function
```
   it("if id pass, check id is valid  ", async () => {
   const response = await requestGetInstanceDetail("i-0b3db6cb7bebde704");
     console.log(response);
     expect(response.id).toEqual("i-0b3db6cb7bebde704");
 });
```
Mocking API request 
```
it("returns the title of the first album", async () => {
  await axios.get.mockResolvedValue({
    data: {
      id: "i-0b3db6cb7bebde704",
      cloudProvider: "aws",
      name: " aws-rnd",
     
  
    },
 

  });

  const response = await requestGetInstanceDetail("i-0b3db6cb7bebde704");
  expect(response).toEqual("i-0b3db6cb7bebde704");
});
```
### Mock React Redux

```
jest.mock("react-redux", () => ({
  ...jest.requireActual("react-redux"),
  useDispatch: jest.fn(),
}));
```
### Mock React Router Dom

```
jest.mock("react-router-dom", () => ({
  ...jest.requireActual("react-router-dom"),
  useHistory: () => ({
    push: jest.fn(),
  }),
}));
```
### Check dispatch function calls times
```
expect(dispatch).toHaveBeenCalledTimes(2);
```
