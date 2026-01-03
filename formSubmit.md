# FormSubmit 

## Client Side
-The inputs in the form needs to have name attribute
```js
async function saveAddress(e: React.FormEvent<HTMLFormElement>) {
   e.preventDefault();

  const form = e.currentTarget;
  const data = new FormData(form);

  await fetch('/api/user/address', {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({
      city: data.get('city'),
      state: data.get('state'),
      zipcode: data.get('zipcode'),
    }),
  });
}   
<form onSubmit={saveAddress}>
  <div className="grid grid-cols-2 gap-4">
    <input name="name" className="input" defaultValue={user?.name ?? ''} />
    <input name="surname" className="input" defaultValue={user?.surname ?? ''} />

    <input name="email" className="input col-span-2" defaultValue={user?.email ?? ''} />
    <input name="phNumber" className="input col-span-2" defaultValue={user?.phNumber?.toString() ?? ''} />

    <input name="city" className="input" defaultValue={user?.address?.city ?? ''} />
    <input name="state" className="input" defaultValue={user?.address?.state ?? ''} />
    <input name="zipcode" className="input" defaultValue={user?.address?.zipcode ?? ''} />

    <textarea name="description" className="input col-span-2" />
  </div>

  <button type="submit">Save Address</button>
</form>

```