# next.js Cheat Sheet

<br><br>

## Guides 
- https://www.youtube.com/watch?v=kVddMV-TrSw&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=2
  - https://github.com/gopinav/Next.js-14-Tutorials
    
<br><br>

## Extensions
- https://chromewebstore.google.com/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en&pli=1


## FAQ

### Slot is not rendered in dev modus
- Try to restart npm run dev sometimes it is buggy..














<br><br>
<br><br>
___________________________________________________
___________________________________________________

<br><br>
<br><br>

# Create app
```shell
cd ~/Projects
npx create-next-app@latest app-name-here
npx next telemetry disable
```

<br><br>

# Start app
```shell
npm run dev
```


# Telemetry
- https://nextjs.org/telemetry

## Disable Telemetry
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

<br><br>

#### global.css
- Global CSS settings

<br><br>

#### layout.tsx
- https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#layouts-layouttsx

<br><br>

#### page.tsx
- https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#page-pagetsx

<br><br>

#### template.tsx
- https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#page-pagetsx

<br><br>

#### not-found.tsx
- [https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#page-pagetsx](https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#404)

<br><br>

#### loading.tsx
- https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#loading-ui-loadingtsx


<br><br>

#### error.tsx
- https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#error-handling-errortsx

















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
```javascript
"scripts": {
    "dev": "next dev"
}
```

<br><br>

### build
- Will build your application. In order to run it you must use the start run script
```javascript
"scripts": {
    "build": "next build"
}
```

<br><br>

### start
- Will start your application. In order to run it you must build the application before with build run script
```javascript
"scripts": {
    "start": "next start"
}
```






















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

# Page (page.tsx)
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
















<br><br>
<br><br>


### Active Links
- If you have e.g. an navbar and you want to add custom css to the current active route segment you can use usePathname()

<br><br>
  
In this example we included Tailwind to style.css
```javascript
@tailwind base;
@tailwind components;
@tailwind utilities;
```

<br><br>

And then added to src/app/(auth)/layout.tsx
- In order to use usePathname() client-side we must 'use client' at the top
```javascript
'use client'

import Link from 'next/link'
import { usePathname } from 'next/navigation'
import './style.css'

const navLinks = [
    { name: 'Register', href: '/register' },
    { name: 'Login', href: '/login' },
    { name: 'Forgot Password', href: '/forgot-password' }
]

/**
 * Renders the layout for the authentication pages.
 * 
 * @param {Object} props - The component props.
 * @param {React.ReactNode} props.children - The child components to render.
 * @returns {React.ReactNode} The rendered layout component.
 */
export default function AuthLayout({
    children
}: {
  children: React.ReactNode;
}) {
    const pathname = usePathname()

    return (
        <div>
            {navLinks.map(link => {
                const isActive = pathname.startsWith(link.href)

                return (
                    <Link href={link.href}
                        key={link.name}
                        className={isActive ? 'font-bold mr-4' : 'text-blue-500 mr-4'}>
                        {link.name}
                    </Link>
                )
            })}
        </div>
    )
}
```
- If you visit localhost:3000/register you will see the Register link will be bold because it is the active route segment
















<br><br>
<br><br>


### Navigating Programmatically
- If you want that a user clicks on a button to place and order and if the order is successfully he get redirected back to home page you would create src/app/order-product/page.tsx
```javascript
'use client'

import { useRouter } from 'next/navigation'

/**
 * Renders the Order Product page.
 * @returns {JSX.Element} JSX element representing the Order Product page.
 */
export default function OrderProduct() {
    const router = useRouter()

    const handleClick = () => {
        console.log('Placing your order..')
        router.push('/')

        // router.push('/blog') // In this example we use / as root for router.push('/') put you can use any route segment for and href link component you have defined in other files

        // router.replace('/') // If needed you can also use router.replace('/'). This is equal to the replace tag in your link component where you clear the history for going back

        // router.back() // Will go back to the previous page
        // router.forward() // Will go to the next page
    }

    return (
        <>
            <h1>Order Product</h1>
            <button onClick={handleClick}>Place order</button>
        </>
    )
}
```
- useRouter() only works client-side so we add 'use client' to the top
- In this example we use / as root for router.push('/') put you can use any route segment for and href link component you have defined in other files
- If needed you can also use router.replace('/'). This is equal to the replace tag in your link component where you clear the history for going back
































<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>





# Templates (template.tsx)
- Templates are similar to layouts in that they wrap each child layout or page

- But, with templates, when a user navigates between routes that share a template, a new instance of the component is mounted, DOM elements are recreated, state is not preserved, and effects are re-synchronized

- A template can be defined by exporting a default React component from a template.js or template.tsx file

- Similar to layouts, templates also should accept a children prop which will render the nested segments in the route.





<br><br>
<br><br>

## Example not using Template
- If you define e.g. an input button in your src/app/(auth)/layout.tsx then the state will bis pre-served when you would enter something inside of the input and then switch the side to e.g. from route localhost:3000/register to reout localhost:3000/login
  - This is because layout only represents the content of the currently loaded page and common elements will be keeped untouched
  - layouts do not re-mount shared components which will result in better performance
```javascript
'use client'

import Link from 'next/link'
import { usePathname } from 'next/navigation'
import './style.css'
import { useState } from 'react'

const navLinks = [
    { name: 'Register', href: '/register' },
    { name: 'Login', href: '/login' },
    { name: 'Forgot Password', href: '/forgot-password' }
]

/**
 * Renders the layout for the authentication pages.
 * 
 * @param {Object} props - The component props.
 * @param {React.ReactNode} props.children - The child components to render.
 * @returns {React.ReactNode} The rendered layout component.
 */
export default function AuthLayout({
    children
}: {
  children: React.ReactNode;
}) {
    const pathname = usePathname()
    const [input, setInput] = useState('')

    return (
        <div>
            <div>
                <input
                    type="text"
                    value={input}
                    onChange={e => setInput(e.target.value)}
                />
                <button onClick={() => console.log(input)}>Search</button>
            </div>

            {navLinks.map(link => {
                const isActive = pathname.startsWith(link.href)

                return (
                    <Link href={link.href}
                        key={link.name}
                        className={isActive ? 'font-bold mr-4' : 'text-blue-500 mr-4'}>
                        {link.name}
                    </Link>
                )
            })}
        </div>
    )
}
```

<br><br>
<br><br>

## Example template
- Rename layout.tsx to template.tsx
  - Use the same code from above at "Example not using Template"
    - As you can see now the state is no pre-served anymore and the input field is cleared because an new instance will be created

- **You can use layout.tsx and template.tsx together**
  - They layout.tsx renders first and children will be replaced by the components exported of the template.tsx file





























<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>

# Loading UI (loading.tsx)
- This file allows us to create loading states that are displayed to users while a specific route segments content is loading
- The loading state appears immediately upon navigation, giving users the assurance that the application is responsive and actively loading content
- **This file will wrap the page.tsx file and all it nested children**

<br><br>

## Benefits
- You can display the loading state as soon as a user navigates to a new route. The immediate feedback reassures users that their action has been acknowledged, reduces perceived loading times, and makes the application feel more responsive.

- Next.js allows the creation of shared layouts that remain interactive while new route segments are loading. Users can continue interacting with certain parts of the application, such as a navigation menu or sidebar, even if the main content is still being fetched

<br><br>

## Example
1. Create e.g. src/app/blog/loading.tsx
```javascript
/**
 * Renders the Loading page.
 * @returns {JSX.Element} JSX element representing the Loading page.
 */
export default function Loading() {
    return <h1>Loading</h1>
}
```

2. Add timeout to your src/app/blog/page.tsx
```javascript
import { Metadata } from 'next'

export const metadata: Metadata = {
    title: 'Blog'
}

/**
 * Renders the Blog page.
 * @returns {JSX.Element} JSX element representing the Blog page.
 */
export default async function Blog() {
    await new Promise(resolve => setTimeout(resolve, 2000))

    return (
        <>
            <h1>Blog</h1>
        </>
    )
}
```
- If you visit now http://localhost:3000/blog you will the loading text from loading.tsx until page.tsx is fully loaded






































<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>

# Error Handling (error.tsx)
- Will be wrapped around your related page.tsx 
- Other components are still running and the app is not crashing and you can handle the error
  - e.g. redirect or make a page reload


<br><br>
<br><br>

## Example Hierarchy
- Expecting you have thw following files:
  - layout.js
  - template.js
  - error.js
  - loading.js
  - not-found.js
  - page.js

- You would have this layer Hierarchy for the handling:
```javascript
<Layout>
  <Template>
    <ErrorBoundary fallback={<Error />}>
      <Suspense fallback={<Loading />}>
        <ErrorBoundary fallback={<NotFound />}>
          <Page />
        </ErrorBoundary>
      </Suspense>
    </ErrorBoundary>
  </Template>
</Layout>
```


<br><br>
<br><br>

## Example without error handling
- Image you throw an error e.g. in src/app/products/[productId]/reviews/[reviewId]/page.tsx
```javascript
import { notFound } from 'next/navigation'

/**
 * Generates a random integer between 0 and the specified count.
 * @param {number} count - The upper bound for the random integer.
 * @returns {number} The generated random integer.
 */
function getRandomInt(count: number) {
    return Math.floor(Math.random() * count)
}

/**
 * Renders the review page for a specific review ID and product ID.
 * @param {Object} params - The parameters object containing the review ID and product ID.
 * @param {string} params.reviewsId - The review ID.
 * @param {string} params.productId - The product ID.
 * @returns {JSX.Element} The rendered review page.
 */
export default function ReviewsId({ params }: {
      params: { reviewsId: string, productId: string }
   }) {
    const random = getRandomInt(2)

    if (random === 1) {
        throw new Error('Random error')
    }

    if (parseInt(params.reviewsId) > 1000) {
        notFound()
    }

    return (
        <>
            <h1> Review { params.reviewsId } for product { params.productId } </h1>
        </>
    )
}
```
- In development mode you will see the error with full details when you visit http://localhost:3000/products/1/reviews/500
  - If you build the application (npm run build) and then start the application (npm run start) you will see:
  "Application error: a server-side exception has occurred (see the server logs for more information).
Digest: 1685611821"
    - Further details can then be seen in the terminal log

- **The biggest problem is that your app will crash and other components are not available any more**






<br><br>
<br><br>

## Example with error handling
- Create e.g. src/app/products/[productId]/reviews/[reviewId]/error.tsx
```javascript
'use client'

/**
 * Error page.
 * @returns {JSX.Element} JSX element representing the Error page.
 */
export default function ErrorBoundary({ error }: { error: Error
}) {
    return <h1>Error message: {error.message}</h1>
}
```













<br><br>
<br><br>

## Recovering from Errors
- In some cases you may want to retry if an error occurs. As example if you fetch data. For this case you can use reset:
```javascript
'use client'

/**
 * Error page.
 * @returns {JSX.Element} JSX element representing the Error page.
 */
export default function ErrorBoundary({
    error, reset
}: {
    error: Error,
    reset: () => void
}) {
    return (
        <div>
            <h1>Error: {error.message}</h1>
            <br></br>
            <button onClick={reset}>Try again</button>
        </div>
    )
}
```
- In page.ts you woudl have to set 'use client'


















<br><br>
<br><br>


## Handling Errors in Nested Routes
- Errors bubble up to the closed parent error boundary
  - An error.tsx file will catch all errors from all nested child segements
    - By positioning error.tsx files at different levels in the nested folders of a route, you can achieve a more granular level of error handling


E.g. remove src/app/products/[productId]/reviews/[reviewdId]/error.tsx to:
- src/app/products/error.tsx


This means any error which happen in e.g. http://localhost:3000/products/1/reviews/* will bubble up to the nearest parent error.tsx in this case:
- src/app/products/error.tsx

**This also means if you place your error.tsx file in a parent directory then all nested segment layout.tsx files will not be loaded and ignored. Like e.g.:**
- src/app/products/[productId]/layout.tsx


















<br><br>
<br><br>

## Handling Errors in Layouts
- An error.tsx file will handle error for all its nested child segments
- The error boundary does not catch error error thrown in layouts because from the hierarchy it's nested inside the layouts component
```javascript
<Layout>
  <Template>
    <ErrorBoundary fallback={<Error />}>
      <Suspense fallback={<Loading />}>
        <ErrorBoundary fallback={<NotFound />}>
          <Page />
        </ErrorBoundary>
      </Suspense>
    </ErrorBoundary>
  </Template>
</Layout>
```
  - E.g. copy src/app/products/[productId]/reviews/[reviewId]/error.tsx to:
    - src/app/products/[productId]/error.tsx

  - Then similate an error in rc/app/products/[productId]/layout.tsx
  ```javascript
	  /**
	 * Generates a random integer between 0 and the specified count.
	 * @param {number} count - The upper bound for the random integer.
	 * @returns {number} The generated random integer.
	 */
	function getRandomInt(count: number) {
	    return Math.floor(Math.random() * count)
	}


	/**
	 * Renders the layout for the product page.
	 * @param {{ children: React.ReactNode }} props - The props object containing the 'children' property.
	 * @returns {React.ReactNode} The rendered layout.
	 */
	export default function ProductLayout({
	    children
	}: {
	   children: React.ReactNode;
	 }) {
	    const random = getRandomInt(2)

	    if (random === 1) {
	        throw new Error('Error loading product layout')
	    }

	    return (
	        <>
	            {children}
	            <h2>Product Features</h2>
	        </>
	    )
	}
  ```
  - **This means there will be no error handling because the layout.tsx file is in hierarchy higher than the error and the application will crash**
    - In order to fix this hierarchy problem remove src/app/products/[productId]/error.tsx into:
      - src/app/products/error.tsx
        - Now the error will be catched and handled this is because the error.tsx file is higher than where the error occured in the layout.tsx file
       







































<br><br>
<br><br>
____________________________________________________
____________________________________________________
<br><br>
<br><br>


## Parallel Routes
- Parallel routes are an advanced routing mechanism that akkiws for the simultaneous rendering of multiple pages withing the same layout
  - Image you would build an dashboard with multiple components e.g.:
    - Notifications
    - User analytics
    - Revenue metrics

- Parallel routes are defined using a feature known as slots
  - Slots help structure our content in a modular fashion
  - To define a slot, we use the `@folder` naming convention
  - Each slot in then passed as a prop to its corresponding `layout.tsx` file


<br><br>

### Benefits
- A clear benefit is their ability to split a single layout into various slots, making the code more manageable
- Independent route handling
- Sub-navigation


<br><br>


### Independent route handling
- Each slot of your layout, such as user analytics or revenue metrics, can have its own loading and error states
- This granular control is particulary beneficial in scenarios where different sections of the page load at varying speeds or encounter unique errors


<br><br>


### Sub-navigation in routes
- Each slot of your dashboard can essentially function as a mini-application, complete with its own navigation and state management
- This is especially useful in a complex application such as our dashboard where different sections service disctinct purposes




<br><br>
<br><br>
____________________________________________________
____________________________________________________
<br><br>
<br><br>








<br><br>
<br><br>

### Example
- Create src/app/complex-dashboard/layout.tsx
```javascript
/**
 * Dashboard layout component.
 *
 * @param {Object} props - The component props.
 * @param {React.ReactNode} props.children - The child components to render.
 * @param {React.ReactNode} props.users - The users component to render.
 * @param {React.ReactNode} props.revenue - The revenue component to render.
 * @param {React.ReactNode} props.notifications - The notifications component to render.
 * @returns {JSX.Element} The rendered Dashboard layout.
 */
export default function DashboardLayout({
    children,
    users,
    revenue,
    notifications
}: {
     children: React.ReactNode;
     users: React.ReactNode;
     revenue: React.ReactNode;
     notifications: React.ReactNode;
}) {
    return (
        <div>
            <div>{children}</div>

            <div style={{ display: ''flex }}>
                <div style={{ display: 'flex', flexDirection: 'column' }}>
                    <div>{users}</div>
                    <div>{revenue}</div>
                </div>

                <div style={{ display: 'flex', flex: 1 }}>
                    <div>{notifications}</div>
                </div>
            </div>
        </div>
    )
}
```
- children is equal to complex-dashboard/@children/page.tsx
  - So technically e have 4 slots inside of our layout file


<br><br>
<br><br>

- Create src/app/complex-dashboard/page.tsx
```javascript
/**
 * Renders the Complex Dashboard page.
 * @returns {JSX.Element} JSX element representing the Complex Dashboard page.
 */
export default function ComplexDashboardPage() {
    return <h1>Complex Dashboard</h1>
}
```



<br><br>
<br><br>


- Create src/components/card.tsx
```javascript
/**
 * Renders a card component.
 * @param {Object} props - The component props.
 * @param {React.ReactNode} props.children - The content of the card.
 * @returns {JSX.Element} The rendered card component.
 */
const Card = ({
    children
}: {
       children: React.ReactNode
}) => {
    const cardStyle = {
        padding: '100px',
        margin: '10px',
        boxShadow: '0 4px 8px 0 rgba(0, 0, 0, 0.2)',
        border: '1px solid #ddd',
        display: 'flex',
        justifyContent: 'center',
        alignItems: 'center'
    }
 
    return <div style={cardStyle}>{children}</div>
}

export default Card
```



<br><br>
<br><br>

#### Slots
- Slots will not effect the url structure


<br><br>

- Create src/app/complex-dashboard/@notifications/page.tsx
```javascript
import Card from '@/components/card'

/**
 * Renders the Notifications page.
 * @returns {JSX.Element} JSX element representing the Notifications page.
 */
export default function Notifications() {
    return <Card>Notifications</Card>
}
```

<br><br>

- Create src/app/complex-dashboard/@revenue/page.tsx
```javascript
import Card from '@/components/card';

/**
 * Renders the Revenue page.
 * @returns {JSX.Element} JSX element representing the Revenue page.
 */
export default function Revenue() {
    return <Card>Revenue</Card>
}
```

<br><br>

- Create src/app/complex-dashboard/@users/page.tsx
```javascript
import Card from '@/components/card'

/**
 * Renders the Users page.
 * @returns {JSX.Element} JSX element representing the Users page.
 */
export default function Users() {
    return <Card>Users</Card>
}
```



















































<br><br>
<br><br>
____________________________________________________
____________________________________________________
<br><br>
<br><br>





## Unmatched Routes

### Navigation from the UI
- In the case of navigation within the UI, Next.js retains the previously active state of a slot regardless of changes in the URL
  - This means other slots keep uneffected

### Page reload
- Next.js immediately searches for a default.tsx file within each unmatched slot
   - The presence of this file is critical, as it provides the default content that Next.js will render in the UI
     - If this default.tsx file is missing in any of the unmatched slots for the current route, Next.js will render a 404 error
       - **This means if you will click on the archived link from the example below and then reload the page for http://localhost:3000/complex-dashboard/archived then you would get a 404**
         - This is because there is no default.tsx file in the children:
           - src/app/complex-dashboard/@users
           - src/app/complex-dashboard/@revenue


- src/app/complex-dashboard/@notifications/page.tsx
```javascript
import Card from '@/components/card'
import Link from 'next/link'

/**
 * Renders the Notifications page.
 * @returns {JSX.Element} JSX element representing the Notifications page.
 */
export default function Notifications() {
    return (
        <Card>
            <div>Notifications</div>
            <Link href="/complex-dashboard/archived">Archived</Link>
        </Card>
    )
}
```

<br><br>

- src/app/complex-dashboard/@notifications/archived/page.tsx
```javascript
import Card from '@/components/card'
import Link from 'next/link'

/**
 * Renders the Archived Notifications page.
 * @returns {JSX.Element} JSX element representing the Archived Notifications page.
 */
export default function ArchivedNotifications() {
    return (
        <Card>
            <div>Archived Notifications</div>
            <Link href="/complex-dashboard">Default</Link>
        </Card>
    )
}
```




<br><br>
<br><br>

### default.tsx
- The `default.tsx` file in Next.js serves as a fallback to render content when the framework cannot retrieve a slots active state from the current url
- you have complete freedom to define the UI for unmatched routes. You can either mirror the content found in page.tsx or craft an entirely custom view

<br><br>
<br><br>

#### Examples
- In order to prevent 404 when you visit http://localhost:3000/complex-dashboard/archived create:
    - src/app/complex-dashboard/default.tsx
      - This is the fallback for the children slot
      ```javascript
      /**
		 * Renders the Default Complex Dashboard page.
		 * @returns {JSX.Element} JSX element representing the Default Complex Dashboard page.
		 */
		export default function DefaultComplexDashboardPage() {
		    return <h1>Complex Dashboard</h1>
		}
      ```

    - src/app/complex-dashboard/@users/default.tsx
      ```javascript
		import Card from '@/components/card'

		/**
		 * Renders the Default Users page.
		 * @returns {JSX.Element} JSX element representing the Default Users page.
		 */
		export default function DefaultUsers() {
		    return <Card>Users</Card>
		}
      ```

    - src/app/complex-dashboard/@revenue/default.tsx
      ```javascript
		import Card from '@/components/card'

		/**
		 * Renders the Default Revenue page.
		 * @returns {JSX.Element} JSX element representing the Default Revenue page.
		 */
		export default function DefaultRevenue() {
		    return <Card>Revenue</Card>
		}
      ```










































<br><br>
<br><br>
_________________________________________________
_________________________________________________
<br><br>
<br><br>

## Conditional Routes
- Decide which content should be rendered by using conditions

<br><br>

1. Create src/app/complex-dashboard/@login/page.tsx:
```javascript
import Card from '@/components/card'

/**
 * Renders the Login page.
 * @returns {JSX.Element} JSX element representing the Login page.
 */
export default function Login() {
    return <Card>Login</Card>
}
```

<br><br>

2. Import new login slot to src/app/complex-dashboard/layout.tsx:
- If isLoggedIn=false then the login slot will be rendered
```javascript
/**
 * Dashboard layout component.
 *
 * @param {Object} props - The component props.
 * @param {React.ReactNode} props.children - The child components to render.
 * @param {React.ReactNode} props.users - The users component to render.
 * @param {React.ReactNode} props.revenue - The revenue component to render.
 * @param {React.ReactNode} props.notifications - The notifications component to render.
  * @param {React.ReactNode} props.login - The login component to render.
 * @returns {JSX.Element} The rendered Dashboard layout.
 */
export default function DashboardLayout({
    children,
    users,
    revenue,
    login,
    notifications
}: {
     children: React.ReactNode;
     users: React.ReactNode;
     revenue: React.ReactNode;
     login: React.ReactNode;
     notifications: React.ReactNode;
}) {
    const isLoggedIn = false

    return isLoggedIn ? (
        <div>
            <div>{children}</div>

            <div style={{ display: 'flex' }}>
                <div style={{ display: 'flex', flexDirection: 'column' }}>
                    <div>{users}</div>
                    <div>{revenue}</div>
                </div>

                <div style={{ display: 'flex', flex: 1 }}>
                    <div>{notifications}</div>
                </div>
            </div>
        </div>
    ) : ( 
        <div>
            <h1>Sign-in</h1>
            <div>{login}</div>
        </div>
    )
}
```











































<br><br>
___________________________________
___________________________________
<br><br>





## Intercepting Routes
- Intercepting routes allow you to intercept or stop the default routing behaviour to present an alternate view or component when navigating through the UI, while still preserving the indended route for scenarious like page reload
  - This can be useful if you want to show a route while keeping the context of the current page
    - **This means if you want e.g. to open a image from a gallery within the same site on a modal box**
    - If you reload the page or somebody opens this url directly then they will be redirected to the original component and not the inetrcepted

<br><br>
<br><br>

### Conventions
- (.) to match segments on the same level
  - The folder must be on the same layer where the original folder is

- (..) to match segments one level above

- (..)(..) to match segments two level above

- (...) to match segments from the root app directory







<br><br>
<br><br>

### (.)

Create `src/app/f1/page.tsx`:
```javascript
import Link from 'next/link'

/**
 * Renders the F1 page.
 * @returns {JSX.Element} JSX element representing the F1 page.
 */
export default function F1() {
    return (
        <>
            <h1>F1 Page</h1>
            <div>
                <Link href="/f1/f2">F2</Link>
            </div>
        </>
    )
}
```

<br><br>
<br><br>


Create src/app/f1/f2/page.tsx:
```javascript
/**
 * Renders the F2 page.
 * @returns {JSX.Element} JSX element representing the F2 page.
 */
export default function F2() {
    return <h1>F2</h1>
}
```


<br><br>
<br><br>

Create src/app/f1/(.)f2/page.tsx:
```javascript
/**
 * Renders the Intercepted F2 page.
 * @returns {JSX.Element} JSX element representing the Intercepted F2 page.
 */
export default function InterceptedF2() {
    return <h1>(.) Intercepted F2</h1>
}
```
- If you visit now `http://localhost:3000/f1/f2` you can see that `src/app/f1/(.)f2/page.tsx` will intercept the route
- **If you reload the page now you will see content of `src/app/f1/f2/page.tsx`**









<br><br>
<br><br>


### (..)

<br><br>

Create src/app/f3/page.tsx:
```javascript
/**
 * Renders the F3 page.
 * @returns {JSX.Element} JSX element representing the F3 page.
 */
export default function F3() {
    return <h1>F3</h1>
}
```


<br><br>
<br><br>

Create src/app/f1/f4/page.tsx:
```javascript
import Link from 'next/link'

/**
 * Renders the F4 page.
 * @returns {JSX.Element} JSX element representing the F4 page.
 */
export default function F4() {
    return (
        <>
            <h1>F4 Page</h1>
            <div>
                <Link href="/f1/f3">F3</Link>
            </div>
        </>
    )
}
```

<br><br>
<br><br>

Create src/app/f1/f4/(..)f3/page.tsx:
```javascript
/**
 * Renders the Intercepted F3 page.
 * @returns {JSX.Element} JSX element representing the Intercepted F3 page.
 */
export default function InterceptedF3() {
    return <h1>(..) Intercepted F3</h1>
}
```
- If you visit now `http://localhost:3000/f1/f4` you will see the content of `src/app/f1/f4/page.tsx`
  - If you click on the f3 Link you will get intercepted by `src/app/f1/f4/(..)f3/page.tsx`
- **If you reload the page now you will see content of `src/app/f1/f3/page.tsx`**









<br><br>
<br><br>


### (...)
- Lets say we need to intercept `src/about/page.tsx` folder while navigating through the `src/app/f1/f4/page.tsx`
  - Create `src/f1/f4/(...)about/page.tsx`:
  ```javascript
   /**
	 * Renders the Intercepted About page.
	 * @returns {JSX.Element} JSX element representing the Intercepted About page.
	 */
	export default function InterceptedAbout() {
	    return <h1>(..) Intercepted About</h1>
	}
  ```

  - Add Link to about:
  ```javascript
    import Link from 'next/link'
  
	/**
	 * Renders the F4 page.
	 * @returns {JSX.Element} JSX element representing the F4 page.
	 */
	export default function F4() {
	    return (
	        <>
	            <h1>F4 Page</h1>
	            <div>
	                <Link href="/f1/f3">F3</Link>
	                <Link href="/about">About</Link>
	            </div>
	        </>
	    )
	}
  ```
    - If you visit now `http://localhost:3000/f1/f4` you will see the content of `src/app/f1/f4/page.tsx`
    - If you click on the about Link you will get intercepted by ``src/f1/f4/(...)about/page.tsx``
    - **If you reload the page now you will see content of `src/app/about/page.tsx`**



