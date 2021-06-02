# Adding Dynamic Styles to a Page
#### We can add Dynamic Styles to a page when required 

Consider the below example where we have to add code to dynamically style the page when ever a blank input is entered :

```
return (
    <form onSubmit={formSubmitHandler}>
      <div className="form-control">
        <label>Course Goal</label>
        <input type="text" onChange={goalInputChangeHandler} />
      </div>
      <Button type="submit">Add Goal</Button>
    </form>
  );
```

We can define a state which will hold the valid values :
```
const [isValid,setIsValid] = useState(true);
```

We can then add the code to set the inline Styles :
```
<label style={{color: !isValid ? 'red' : 'black'}}>Course Goal</label>
```
Inline styles have the highest Priorities, all other are overridden.

More extensive use of Inline styles can be  seen below :

```
    return (
    <form onSubmit={formSubmitHandler}>
      <div className="form-control">
        <label style={{color: !isValid ? 'red' : 'black'}}>Course Goal</label>
        <input style={{
          background: !isValid ? 'salmon' : 'white',
          borderColor: !isValid ? 'red' : '#ccc'
        }} type="text" onChange={goalInputChangeHandler} />
      </div>
      <Button type="submit">Add Goal</Button>
    </form>
  );
```