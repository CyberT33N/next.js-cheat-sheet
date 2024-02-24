# next.js Cheat Sheet

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
  /**
   * Renders the page for a specific product ID.
   * @param {Object} props - The component props.
   * @param {Object} props.params - The parameters object containing the product ID.
   * @param {string} props.params.productId - The product ID.
   * @returns {JSX.Element} The rendered page.
   */
  export default function ProductsId({ params }: {
        params: { productId: string }
     }) {
      return (
          <>
              <h1>Product Id: { params.productId }</h1>
          </>
      )
  }
  ```





<br><br>
<br><br>
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

## 404

<br><br>

## default custom not found page
- For default next.js will give you an 404 page. If you want to customize it create src/app/not-found.tsx
```javascript
export default function NotFound() {
   return <h1>404 - Not found..</h1>
}
```

<br><br>

## notFound()
- If needed you can call the default next.js page at a specific point like e.g. at pagination when not items where found anymore
```javascript
import { notFound } from 'next/navigation'

export default function ReviewsId({ params }: {
  params: { reviewsId: string, productId: string }
}) {
  if (parseInt(params.reviewsId) > 1000) {
    notFound()
  }

  return (
    <>
      <h1> Review { params.reviewsId } for product { params.productId } </h1>
    </>
  );
}
```
  - If you want to use a custom 404 page then create a not-found.tsx inside of the folder where you call notFound() - In this case:
    - src/app/products/[productId]/reviews/[reviewsId]/not-found.tsx








<br><br>
<br><br>
<br><br>
<br><br>





## Route Groups
- Allows us to logically group our routes and project files without affecting the UTL path structure
- It is usefully to grouo components and make it more easy to work with or to structure for yourself or other developers

1. As example create the folders src/app/login, src/app/register & src/app/forgot-password

2. Create components
- src/app/auth/register/page.tsx
```javascript
export default function Register() {
  return <h1> Register </h1>
}
```
  - localhost:3000/auth/register

- src/app/auth/login/page.tsx
```javascript
export default function Login() {
  return <h1> Login </h1>
}
```
  - localhost:3000/auth/login

- src/app/auth/forgot-password/page.tsx
```javascript
export default function ForgotPassword() {
  return <h1> Forgot Password </h1>
}
```
  - localhost:3000/auth/forgot-password

3. If you do want to have /auth in your url you can rename the folder to:
- src/app/(auth)
  - After this you still have route grouping but you can call:
    - localhost:3000/register
    - localhost:3000/login
    - localhost:3000/forgot-password


























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
- Only the content of this file is sended to the app router.
  - This means if you would create a file file called src/app/dashboard/test.tsx and then visit localhost:3000/dashboard you would get an 404
- You must export an default function or you will get an error when visiting the route
- Only the code inside of the default function will be returned/rendered to the client. This means you can create components inside of this file or in a different location and then import them in your page.tsx file and use them inside the default function

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




































<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>


# Private Folders
- Should not be considered by the routing system
  - Also subfolder are excluded from the routing

- Prefix the folder with underscore e.g. src/app/_lib
  - If you want to include underscore in URL segments you can prefix the folder name with "%5F" which is the URL-encoded from an underscore

- Usefully for seperating UI logic from routing logic
  - Organazing internal files accross a project
  - Avoid potention name conflicts with futre next.js files
 

































<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>

# Layouts (layout.tsx)
- A layout is UI that is shared between multiple pages

<br><br>
<br><br>

## Root Layout (src/app/layout.tsx)
- This component should accept a children pop that will be populated with a child page during rendering
- children of RootLayout will refer to default component in page.tsx

- **src/app/layout.tsx is the root layout**
  - Even when you delete the file it will be auto genrated again. Delete it and navigate again to http://localhost:3000
```javascript
import type { Metadata } from 'next'
import { Inter } from 'next/font/google'
import './globals.css'

const inter = Inter({ subsets: ['latin'] })

export const metadata: Metadata = {
    title: 'Create Next App',
    description: 'Generated by create next app'
}

/**
 * Root layout component.
 *
 * @param {React.ReactNode} children - The child components to render.
 * @returns {JSX.Element} The rendered root layout.
 */
export default function RootLayout({
    children
}: Readonly<{
  children: React.ReactNode;
}>) {
    return (
        <html lang="en">
            <body className={inter.className}>
                <header style={{ padding: '1rem', backgroundColor: 'lightgray' }}>
                    <h1>Header</h1>
                </header>

                {children}

                <footer style={{ padding: '1rem', backgroundColor: 'ghostwhite' }}>
                    <h1>Footer</h1>
                </footer>
            </body>
        </html>
    )
}
```
  - children will be replace by src/app/page.tsx
  - You can call any route like e.g. localhost:3000/anyPage and the root layout will be loaded.
    - This means if you have the file localhost:3000/anyPage/page.tsx then this will be used for the children replacement


<br><br>
<br><br>

## Nested Layout (src/app/anyPage/layout.tsx)
- You can create more custom nested layout.tsx to any page like e.g. src/app/anyPage/layout.tsx
  - However, the root layout will be always loaded first and the nested layout will extend from it. **But the children from src/app/page.tsx will be ignored an instead it will be loaded from your page.tsx location where you put you nested layout.tsx**
```javascript
/**
 * Root layout component.
 *
 * @param {React.ReactNode} children - The child components to render.
 * @returns {JSX.Element} The rendered root layout.
 */
export default function AboutLayout({
    children
}: {
   children: React.ReactNode;
 }) {
    return (
        <>
            {children}
            <h2>Any Text</h2>
        </>
    )
}
```
























<br><br>
<br><br>

## Route Group Layout

1. Create src/app/(auth)/(with-auth-layout)

2. Move register & login folder into src/app/(auth)/with-auth-layout
  - src/app/(auth)/(with-auth-layout)/register/page.tsx
  - src/app/(auth)/(with-auth-layout)/login/page.tsx

3. Create src/app/(auth)/(with-auth-layout)/layout.tsx
```javascript
/**
 * Root layout component.
 *
 * @param {React.ReactNode} children - The child components to render.
 * @returns {JSX.Element} The rendered root layout.
 */
export default function AuthLayout({
    children
}: {
    children: React.ReactNode;
  }) {
    return (
        <div>     
            <h2>Inner Layout</h2>
            {children}
        </div> 
    )
}
```
- If you visit http://localhost:3000/login or http://localhost:3000/register you will notice:
  - Layout of group will be loaded - src/app/(auth)/(with-auth-layout)/layout.tsx
  - The page.tsx will of login will be loaded because there we require the children from

- If you visit http://localhost:3000/forgot-password then the layout group will be not loaded because the foder is only inside of (auth)















































<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>


# Metadata

<br><br>
<br><br>

## Routing Metadata
- Ensuring proper search engine optimization (SEO) is crucial for increasing visibility and attracting users
- Next.js introduced the Metadata API which allows you to define metadata for each page
- Metadata ensures accurate and relevant information is displayed when your pages are shared or indexed


## Configuring Metadata
- Export a static metadata object
- Export a dynamic generateMetadata function

### Metadata rules
- Both layout.tsx and page.tsx files can export metadata. If defined in a layout, it applies to all pages in that layout, but if defined in a page, it applies only to that page
- Metadata is read in order, from the root level down to the final page level
- When there's metadata in multiple places for the same route, they get combined, but page metadata will replace layout metadata if they have the same properties










<br><br>
<br><br>






## Static metadata object
1. Keep the metadata in src/app/layout.tsx
```javascript
import type { Metadata } from 'next'
import { Inter } from 'next/font/google'
import './globals.css'

const inter = Inter({ subsets: ['latin'] })

export const metadata: Metadata = {
    title: 'Create Next App',
    description: 'Generated by create next app'
}

/**
 * Root layout component.
 *
 * @param {React.ReactNode} children - The child components to render.
 * @returns {JSX.Element} The rendered root layout.
 */
export default function RootLayout({
    children
}: Readonly<{
  children: React.ReactNode;
}>) {
    return (
        <html lang="en">
            <body className={inter.className}>
                <header style={{ padding: '1rem', backgroundColor: 'lightgray' }}>
                    <h1>Header</h1>
                </header>

                {children}

                <footer style={{ padding: '1rem', backgroundColor: 'ghostwhite' }}>
                    <h1>Footer</h1>
                </footer>
            </body>
        </html>
    )
}
```

2. Add to src/app/about/page.tsx
```javascript
export const metadata = {
	title: 'About'
}

/**
 * Renders the About page.
 * @returns {JSX.Element} JSX element representing the About page.
 */
export default function About() {
    return <h1>About</h1>
}
```
- layout.tsx and page.tsx can have metadata
  - But page.tsx has higher prio if both exists and would overwrite/merge properties
    - This means if you would visit localhost:3000 then you would see:
    ```html
    <title>Create Next App</title>
    <meta name="description" content="Generated by create next app">
    ```
      - If you would visit localhost:3000/about then you would see:
       ```html
	    <title>About</title>
	    <meta name="description" content="Generated by create next app">
	    ```













<br><br>
<br><br>


## Dynamic metadata object
- We define the generateMetadata function for this case
- You can not export the generateMetadata function and the default metadata together
```javascript
import { Metadata } from 'next'

type Props = {
     params: {
           productId: string
     }
}

export const generateMetadata = ({ params}: Props): Metadata => {
    return {
        title: `Product Id: ${params.productId}`,
        description: `This is the product page for product ID: ${params.productId}.`
    }
}

/**
 * Renders the page for a specific product ID.
 * @param {Object} props - The component props.
 * @param {Object} props.params - The parameters object containing the product ID.
 * @param {string} props.params.productId - The product ID.
 * @returns {JSX.Element} The rendered page.
 */
export default function ProductsId({ params }: Props) {
    return (
        <>
            <h1>Product Id: { params.productId }</h1>
        </>
    )
}
```
- If you navigate to localhost:3000/products/1 you will see:
	```
	<title>Product Id: 1</title>
    <meta name="description" content="Generated by create next app">
	```
- If you navigate to localhost:3000/products/100 you will see:
	```
	<title>Product Id: 100</title>
    <meta name="description" content="Generated by create next app">
	```

<br><br>


- Works aswell with async:
```javascript
import { Metadata } from 'next'

type Props = {
     params: {
           productId: string
     }
}

export const generateMetadata = async ({ params}: Props): Promise<Metadata> => {
    const serialNumber = await fetch('xxxxxxxx')

    return {
        title: `Product Id: ${params.productId} - Serial number: ${serialNumber}`,
        description: `This is the product page for product ID: ${params.productId}.`
    }
}

/**
 * Renders the page for a specific product ID.
 * @param {Object} props - The component props.
 * @param {Object} props.params - The parameters object containing the product ID.
 * @param {string} props.params.productId - The product ID.
 * @returns {JSX.Element} The rendered page.
 */
export default function ProductsId({ params }: Props) {
    return (
        <>
            <h1>Product Id: { params.productId }</h1>
        </>
    )
}
```





















<br><br>
<br><br>

## Title - Metadata
- Defines the document title
- Can be string or object
  - String - src/app/about/page.tsx:
  ```javascript
	export const metadata = {
	    title: 'About'
	}
	
	/**
	 * Renders the About page.
	 * @returns {JSX.Element} JSX element representing the About page.
	 */
	export default function About() {
	    return <h1>About</h1>
	}
  ```
 - Object - src/app/about/page.tsx:
  ```javascript
	import { Metadata } from 'next'
	
	export const metadata: Metadata = {
	    title: {
	        absolute: 'Completly overwrite',
	        default: 'Will be used as fallback title',
	        template: '%s | Extendend Information'
	    },
	    description: "This is the about page"
	}
	
	/**
	 * Renders the About page.
	 * @returns {JSX.Element} JSX element representing the About page.
	 */
	export default function About() {
	    return <h1>About</h1>
	}
  ```
  - absolute will overwrite title for all child route segments
    - If you set template but you do not want it in specific chil segments then do:
    ```
        import { Metadata } from 'next'

	export const metadata: Metadata = {
	    title: {
	        absolute: 'Custom Title',
	    },
	}
	
	/**
	 * Renders the Blog page.
	 * @returns {JSX.Element} JSX element representing the Blog page.
	 */
	export default function Blog() {
	    return <h1>Blog</h1>
	}
    ```
      - This means if will ignore the absolute & template key from the parent route segment

  - default will be used as fallback title for all child route segments
    - This means src/app/about/childPage/page.tsx would use it aswell
      
  - template will extend metadata title in all child route segments e.g. src/app/about/company/page.tsx:
    ```
        import { Metadata } from 'next'

	export const metadata: Metadata = {
	    title: 'Blog'
	}
	
	/**
	 * Renders the Blog page.
	 * @returns {JSX.Element} JSX element representing the Blog page.
	 */
	export default function Blog() {
	    return <h1>Blog</h1>
	}
    ```
    - So it will be
      ```html
      <title>Blog | Extendend Information</title>
      <meta name="description" content="Generated by create next app">
      ```










































<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>

## Link Component Navigation
- Using UI elements like links to navigate or programmatic navigation

### Link component
- Next.js provide the link component for client-side navigation

- src/app/page.tsx
```javascript
import Link from 'next/link'

/**
 * Renders the home page.
 * @returns {JSX.Element} The rendered home page.
 */
export default function Home() {
    return <>
        <h1>Welcome home!</h1>
        <Link href="/blog">Blog</Link>
        <br></br>
        <Link href="/products">Products</Link>
    </>
}
```
  - If you want to go back to the home page e.g. /src/app/products/page.tsx:
  ```javascript
	import Link from 'next/link'

	/**
	 * Renders the Products component.
	 * @returns {JSX.Element} JSX element
	 */
	export default function Products() {
	    return (
	        <>
	            <Link href="/">Home</Link>

	            <br></br>

	            <h1>Product List</h1>
	           
	            <h2>Product 1</h2>
	            <h2>Product 2</h2>
	            <h2>Product 3</h2>
	        </>
	    )
	}
  ```

<br><br>
<br><br>

#### Navigate to dynamic routes
```javascript
import Link from 'next/link'

/**
 * Renders the Products component.
 * @returns {JSX.Element} JSX element
 */
export default function Products() {
    return (
        <>
            <Link href="/">Home</Link>

            <br></br>

            <h1>Product List</h1>
           
            <h2><Link href="products/1">Product 1</Link></h2>
            <h2><Link href="products/2">Product 2</Link></h2>
            <h2><Link href="products/3">Product 3</Link></h2>
        </>
    )
}
```
- If we have e.g. 100 products we can use a different way instead of hardcode:
  ```javascript
	import Link from 'next/link'

	/**
	 * Renders the Products component.
	 * @returns {JSX.Element} JSX element
	 */
	export default function Products() {
	    const productId = 100

	    return (
	        <>
	            <Link href="/">Home</Link>

	            <br></br>

	            <h1>Product List</h1>
	           
	            <h2>
	                <Link href={`products/${productId}`}>Product {productId}</Link>
	            </h2>
	        </>
	    )
	}
  ```
  - If needed you can use the replace tag which will clear the history and take you back to the home page if you go back:
    ```javascript
	import Link from 'next/link'

	/**
	 * Renders the Products component.
	 * @returns {JSX.Element} JSX element
	 */
	export default function Products() {
	    const productId = 100

	    return (
	        <>
	            <Link href="/">Home</Link>

	            <br></br>

	            <h1>Product List</h1>
	           
	            <h2><Link href="products/1">Product 1</Link></h2>
	            <h2><Link href="products/2">Product 2</Link></h2>
	            <h2><Link href="products/3" replace>Product 3</Link></h2>

	            <h2>
	                <Link href={`products/${productId}`}>Product {productId}</Link>
	            </h2>
	        </>
	    )
	}
    ```

