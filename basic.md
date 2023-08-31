```js
import React from 'react';
import { useForm } from 'react-hook-form';

function App() {
  const {
    register,
    formState: { errors },
    handleSubmit,
  } = useForm()

  const onSubmit = (data) => {
    console.log(data);
  };

  return (
    <form onSubmit={handleSubmit(onSubmit)}>
      <input
        type="text"
        {...register("username", { required: true })}
      />
      {errors.username && <p>Username is required and should be at least 4 characters.</p>}
      
      <input
        type="password"
        {...register("password", { required: true })}
      />
      {errors.password && <p>Password is required and should be at least 8 characters.</p>}
      
      <button type="submit">Submit</button>
    </form>
  );
}

export default App;
```
