# Handler

## Frontend
-To get Params('/payment?status=success')

## GET Handler
-To get params in a dynamic api like 'api/items/[category]/route.ts'
```js
export async function GET(
  req: Request,
  { params }: { params: { category: string } }
) {
  const category = params.category; 
}

```

## POST Handler
```js
export async function POST(req: Request) {
  const data = await req.json();
  return Response.json({ ok: true });
}

```
### Example req
```js
POST /api/user/address?id=123 HTTP/1.1
Content-Type: application/json
Authorization: Bearer abc123
Cookie: next-auth.session-token=xyz
{
  "name": "Hero",
  "email": "hero@gmail.com",
  "address": {
    "houseNo": "12A",
    "street": "MG Road",
    "landmark": "Near Metro",
    "city": "Hyderabad",
    "state": "Telangana",
    "zipcode": "500001"
  }
}
```
### req properties

1. `req.headers.get('content-type')` to get  "application/json"
2. `req.headers.get('authorization')` to get "Bearer abc123"
3. `const body = await req.json();` to get data sent by the user
4. To get query params - '123'
```js
 const { searchParams } = new URL(req.url)
    searchParams.get('id')
```