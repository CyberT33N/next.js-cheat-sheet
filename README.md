# next.js-cheat-sheet

<br><br>

## Guides 
- https://www.youtube.com/watch?v=kVddMV-TrSw&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=2

<br><br>

### Create app
```shell
cd ~/Projects
npx create-next-app@latest app-name-here
npx next telemetry disable
```

<br><br>

### Start app
```shell
npm run dev
```


### Telemetry
- https://nextjs.org/telemetry

#### Disable Telemetry
- Set this enmvironment variable
```
# Method 1
npx next telemetry disable

# Method #2
NEXT_TELEMETRY_DISABLED=1
```









<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>

# File/FolderStructure

<br><br>

## public
- This folder contains public assets like images



<br><br>
<br><br>

## src
- This folder contains the code

<br><br>

### src/app
- Route folder

#### global.css
- Global CSS settings

#### layout.tsx
- ui that can be shared through different pages in your app
- children of RootLayout will refer to default component in page.tsx

#### page.tsx
- basicly same as index.html
- Auto refresh when you save changes





















<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>

# package.json

<br><br>

## npm run scripts

<br><br>

### dev
- Will execute src/app/layout.tsx
























<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>



# Components

<br><br>

## RSC (React Server Components)
- Introduced in version 18 and it splitting components in two types
- https://github.com/CyberT33N/react.js-cheat-sheet/blob/main/README.md#components
- In next.js all components are server components by default





















<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>



# Routing
- Next.js has a file system based route mechanism
  - This means urls that can be accessed from client are the folder structure

<br><br>
 
## Conventions
- All routes must be placed inside of src/app folder (page.tsx)
  - The folder src/app must always exists
- Files that correspons to a route must be name page.js or page.tsx
- Every folder corresponds to a path segment in the browser URL

<br><br>
<br><br>

## Nested Routing
- https://www.youtube.com/watch?v=mEral6yz130&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=6

- Create e.g. src/app/blog/page.tsx
```javascript
export default function Blog() {
  return (
    <h1>Blog</h1>
  );
}
```
  - Create nested folders and related page.tsx
    - src/app/blog/first/page.tsx
    ```javascript
    export default function FirstBlog() {
      return (
        <h1>First Blog</h1>
      );
    }
    ```
    - src/app/blog/second/page.tsx
    ```javascript
    export default function SecondBlog() {
      return (
        <h1>Second Blog</h1>
      );
    }
    ```
    
<br><br>
<br><br>

## Dynamic Routes
- https://www.youtube.com/watch?v=N4-EkNJ6RFM&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=7
- Is used when want to handle multiple entries e.g. 100 diferent product pages and you do not want to use nested routing for this
- [] are used to define dynamic routes
  - **Name inside of the brackets must be equal to params e.g. params.productId**

- Create e.g. src/app/products/page.tsx
```javascript
export default function Products() {
  return (
    <>
      <h1>Product List</h1>
      
      <h2>Product 1</h2>
      <h2>Product 2</h2>
      <h2>Product 3</h2>
    </>
  );
}
```
  - Create folder src/app/products/[productId]/page.tsx
  ```javascript
  export default function ProductsId({ params }: {
    params: { productId: string }
  }) {
    return (
      <>
        <h1>Product Id: { params.productId }</h1>
      </>
    );
  }
  ```




<br><br>
<br><br>

## Nested Dynamic Routes
- https://www.youtube.com/watch?v=Vn4p4K6_M44&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=8&pp=iAQB
- Check Dynamic Routes before https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#dynamic-routes

- Create e.g. src/app/products/[productId]/reviews/[reviewId]/page.tsx
```javascript
export default function ReviewsId({ params }: {
  params: { reviewsId: string, productId: string }
}) {
  return (
    <>
      <h1> Review { params.reviewsId } for product { params.productId } </h1>
    </>
  );
}
```







<br><br>
<br><br>

## Catch-all Segments
- https://www.youtube.com/watch?v=Ssw6-69KLRo&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=9
- [...NameHere] in your folder name will be used to catch all segments
- This is usefully e.g. for documentation where you have hundreds of pages but you want the same layout
```
localhost:3000/docs/feature1/concept1
localhost:3000/docs/feature1/concept2
localhost:3000/docs/feature2/concept1
localhost:3000/docs/feature2/concept2

20 Features x 20 Concepts = 400
20 Features x 1 [conceptId] = 20
1 [featureId] x 1 [conceptId] = 1
```

- Create e.g. src/app/docs/[...slug]/page.tsx
```javascript
export default function Docs({ params }: {
     params: { slug: string[] }
}) {
     // http://localhost:3000/docs/test/apple
     if (params.slug?.length === 2) {
          return (
          <h1>
               View Docs for feature : { params.slug[0]} and concept: {params.slug[1] }
          </h1>
          )
     } else if (params.slug?.length === 1) {
          // http://localhost:3000/docs/test
          return (
          <h1>
               View Docs for feature : { params.slug[0] }
          </h1>
          )
     }

     // http://localhost:3000/docs/test/apple/third
     return <h1>Docs Home Page</h1>
   }
```
  - This means you will create a base page file which will be used in every path you open with contains under docs e.g.:
    - http://localhost:3000/docs/test
    - http://localhost:3000/docs/test/more
   
  - http://localhost:3000/docs/test so the param /test would be the feature params.slug[0]
    -  http://localhost:3000/docs/test/apple so the /apple would be the concept params.slug[1] 

  - In the Catch-all Segments example from above this url would be 404 http://localhost:3000/docs
    - You can allow it with [[]] e.g. Create e.g. src/app/docs/[[...slug]]/page.tsx which will redirect to the page.tsx











<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>



# page.tsx
```
export default function Home() {
  return (
    <h1>Home</h1>
  );
}
```


# layout.tsx
- This file will be automatically created when you load the root route
```
import type { Metadata } from "next";
import { Inter } from "next/font/google";
import "./globals.css";

const inter = Inter({ subsets: ["latin"] });

export const metadata: Metadata = {
  title: "Create Next App",
  description: "Generated by create next app",
};

export default function RootLayout({
  children,
}: Readonly<{
  children: React.ReactNode;
}>) {
  return (
    <html lang="en">
      <body className={inter.className}>{children}</body>
    </html>
  );
}

```



