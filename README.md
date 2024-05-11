# next.js Cheat Sheet

<br><br>

## Guides 
- https://www.youtube.com/watch?v=kVddMV-TrSw&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=2
  - https://github.com/gopinav/Next.js-14-Tutorials
    
<br><br>

## Chrome Extensions
- https://chromewebstore.google.com/detail/react-developer-tools/fmkadmapgofadopljbjfkapdkoienihi?hl=en&pli=1

<br><br>

## VS Code Extensions
- https://marketplace.visualstudio.com/items?itemName=rangav.vscode-thunder-client
```
# https://docs.pieces.app/installation-getting-started/linux
sudo snap install pieces-os
sudo snap connect pieces-os:process-control :process-control
sudo snap install pieces-for-developers
pieces-os
pieces-for-developers
```


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

# Create your repo via ui 
git remote add github git@github.com:CyberT33N/c0in-suite.git

git push
```

<br><br>

# Init other Projects
```shell
npm i
```


<br><br>

<br><br>

# Start app
```shell
npm run dev
```

<br><br>

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

#### default.tsx
- [https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#error-handling-errortsx](https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#defaulttsx)

<br><br>

#### route.ts
- https://github.com/CyberT33N/next.js-cheat-sheet/blob/main/README.md#route-handlers-routets

<br><br>

#### middleware.ts
- https://github.com/CyberT33N/next.js-cheat-sheet/#middleware
  
<br><br>

#### tsconfig.json











<br><br>
<br><br>

_______________________________________________________
_______________________________________________________

<br><br>
<br><br>


# tsconfig.json
- https://nextjs.org/docs/app/building-your-application/configuring/absolute-imports-and-module-aliases

<br><br>

## Absolute Imports and Module Path Aliases
```
// before
import { Button } from '../../../components/button'
 
// after
import { Button } from '@/components/button'
```
































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









































<br><br>
<br><br>
_________________________________________________________
_________________________________________________________
<br><br>
<br><br>





## Parallel Intercepting Routes
- https://www.youtube.com/watch?v=mVOvx9eVHg0&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=32

<br><br>

1. Clone Project:
- https://github.com/gopinav/Next.js-14-Tutorials

<br><br>

2. Copy `src/app/photo-feed` into your project

<br><br>

3. Copy `src/components/modal.tsx` into your project:
```javascript
'use client'
import { useCallback, useRef, useEffect, MouseEventHandler } from 'react'
import { useRouter } from 'next/navigation'

/**
 * Modal component.
 *
 * @param {{ children: React.ReactNode }} props - The props for the Modal component.
 * @returns {JSX.Element} The rendered Modal component.
 */
export default function Modal({ children }: { children: React.ReactNode }) {
    const overlay = useRef(null)
    const wrapper = useRef(null)
    const router = useRouter()

    const onDismiss = useCallback(() => {
        router.back()
    }, [router])

    const onClick: MouseEventHandler = useCallback(
        e => {
            if (e.target === overlay.current || e.target === wrapper.current) {
                if (onDismiss) onDismiss()
            }
        },
        [onDismiss, overlay, wrapper]
    )

    const onKeyDown = useCallback(
        (e: KeyboardEvent) => {
            if (e.key === 'Escape') onDismiss()
        },
        [onDismiss]
    )

    useEffect(() => {
        document.addEventListener('keydown', onKeyDown)
        return () => document.removeEventListener('keydown', onKeyDown)
    }, [onKeyDown])

    return (
        <div
            ref={overlay}
            className="fixed z-10 left-0 right-0 top-0 bottom-0 mx-auto bg-black/60 p-10"
            onClick={onClick}
        >
            <div
                ref={wrapper}
                // eslint-disable-next-line max-len
                className="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 sm:w-10/12 md:w-8/12 lg:w-2/5 p-6"
            >
                {children}
            </div>
        </div>
    )
}
```

<br><br>

4. Check `src/app/photo-feed/wonders.ts` to understand how it works:
```javascript
import { StaticImageData } from 'next/image'
import photo1 from './photos/1.jpg'
import photo2 from './photos/2.jpg'
import photo3 from './photos/3.jpg'
import photo4 from './photos/4.jpg'
import photo5 from './photos/5.jpg'
import photo6 from './photos/6.jpg'
import photo7 from './photos/7.jpg'

export type WonderImage = {
  id: string;
  name: string;
  src: StaticImageData;
  photographer: string;
  location: string;
};

const wondersImages: WonderImage[] = [
    {
        id: '1',
        name: 'Great Wall of China',
        src: photo1,
        photographer: 'Photo by Max van den Oetelaar on Unsplash',
        location: 'China'
    },
    {
        id: '2',
        name: 'Petra',
        src: photo2,
        photographer: 'Photo by Reiseuhu on Unsplash',
        location: 'Jordan'
    },
    {
        id: '3',
        name: 'Christ the Redeemer',
        src: photo3,
        photographer: 'Photo by Andrea Leopardi on Unsplash',
        location: 'Brazil'
    },
    {
        id: '4',
        name: 'Machu Picchu',
        src: photo4,
        photographer: 'Photo by Jared Schwitzke on Unsplash',
        location: 'Peru'
    },
    {
        id: '5',
        name: 'Chichen Itza',
        src: photo5,
        photographer: 'Photo by E Mens on Unsplash',
        location: 'Mexico'
    },
    {
        id: '6',
        name: 'Roman Colosseum',
        src: photo6,
        photographer: 'Photo by Andrea Cipriano on Unsplash',
        location: 'Italy'
    },
    {
        id: '7',
        name: 'Taj Mahal',
        src: photo7,
        photographer: 'Photo by Su San Lee on Unsplash',
        location: 'India'
    }
]

export default wondersImages
```

<br><br>

5. Check `src/app/photo-feed/page.tsx` to understand how it works:
```javascript
import Link from 'next/link'
import wonders from './wonders'
import Image from 'next/image'

/**
 * Renders the home page of the photo feed.
 * Displays a grid of new wonders of the world with their images and names.
 * @returns {JSX.Element} The rendered home page component.
 */
export default function Home() {
    return (
        <main className="container mx-auto">
            <h1 className="text-center text-3xl font-bold my-4">
        New Wonders of the World
            </h1>
            <div className="grid grid-cols-1 md:grid-cols-4 gap-4">
                {wonders.map(({ id, src, name }) => (
                    <Link key={id} href={`/photo-feed/${id}`}>
                        <Image
                            alt={name}
                            src={src}
                            className="w-full object-cover aspect-square"
                        />
                    </Link>
                ))}
            </div>
        </main>
    )
}
```
- Each image is linked with the link component

<br><br>


6. Check `src/app/photo-feed/[id]/page.tsx` to understand how it works:
```
import Image from 'next/image'
import wondersImages, { WonderImage } from '../wonders'

/**
 * Renders the page for a specific photo.
 * 
 * @param {Object} props - The component props.
 * @param {Object} props.params - The parameters object.
 * @param {string} props.params.id - The ID of the photo.
 * @returns {JSX.Element} The rendered photo page.
 */
export default function PhotoPage({
    params: { id }
}: {
  params: { id: string };
}) {
    const photo: WonderImage = wondersImages.find(p => p.id === id)!
    return (
        <div className="container mx-auto my-10">
            <div className="w-1/2 mx-auto">
                <div>
                    <h1 className="text-center text-3xl font-bold my-4">{photo.name}</h1>
                </div>
                <Image
                    alt={photo.name}
                    src={photo.src}
                    className="w-full object-cover aspect-square "
                />

                <div className="bg-white py-4">
                    <h3>{photo.photographer}</h3>
                    <h3>{photo.location}</h3>
                </div>
            </div>
        </div>
    )
}
```
- E.g. http://localhost:3000/photo-feed/2 will load image 2 of your image array


<br><br>


7. Check `src/app/photo-feed/@modal/(..)photo-feed/[id]/page.tsx` to understand how it works:
```javascript
import Image from 'next/image'
import wondersImages, { WonderImage } from '../../../wonders'
import Modal from '@/components/modal'

/**
 * Renders a modal component displaying details of a photo.
 *
 * @param {Object} props - The component props.
 * @param {Object} props.params - The parameters object.
 * @param {string} props.params.id - The ID of the photo.
 * @returns {JSX.Element} The rendered modal component.
 */
export default function PhotoModal({
    params: { id }
}: {
  params: { id: string };
}) {
    const photo: WonderImage = wondersImages.find(p => p.id === id)!

    return (
        <Modal>
            <Image
                alt={photo.name}
                src={photo.src}
                className="w-full object-cover aspect-square"
            />

            <div className="bg-white p-4">
                <h2 className="text-xl font-semibold">{photo.name}</h2>
                <h3>{photo.photographer}</h3>
                <h3>{photo.location}</h3>
            </div>
        </Modal>
    )
}
```
- This means if you click on an image the interception will fire and load the image by using `src/app/photo-feed/@modal/(..)photo-feed/[id]/page.tsx`
- If you reload the page then it uses `src/app/photo-feed/[id]/page.tsx`


































<br><br>
<br><br>
_________________________________________________________
_________________________________________________________
<br><br>
<br><br>






## Route Handlers (route.ts)
- https://www.youtube.com/watch?v=25yY2RVRq_M&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=33

<br><br>

- Create new project
```shell
cd ~/Projects
npx create-next-app route-handlers-demo
```

<br><br>

### Example 1
- The example below will show you how simple route handling will work

- Create `src/app/hello/route.ts`:
- https://developer.mozilla.org/en-US/docs/Web/API/Response
```javascript
/**
 * Handles the GET request.
 * @returns {Response} The response with the message "Hello World!".
 */
export async function GET() {
    return new Response('Hello World!')
}
```

<br><br>

- Create `src/app/dashboard/route.ts`
```javascript
/**
 * Handles the GET request.
 * @returns {Response} The response with the message "Dashboard".
 */
export async function GET() {
    return new Response('Dashboard')
}
```
- http://localhost:3000/dashboard

<br><br>

- Create `src/app/dashboard/users/route.ts`
```javascript
/**
 * Handles the GET request.
 * @returns {Response} The response with the message "Users".
 */
export async function GET() {
    return new Response('Users')
}
```
- http://localhost:3000/dashboard/users






<br><br>
<br><br>

### Example 1
- The example below will show you how to avoid conflict with route.ts and page.tsx
  - If you create both then the route.ts has higher prio e.g. http://localhost:3000/profile
    - So you will see 'Profile API data'

<br><br>

- Create `src/app/dashboard/profile/page.tsx`
```javascript
/**
 * Renders the Profile page.
 * @returns {JSX.Element} JSX element representing the Profile page.
 */
export default function ProfilePage() {
    return <h1>ProfilePage</h1>
}
```

<br><br>

- Create `src/app/dashboard/profile/route.ts`
```javascript
/**
 * Handles the GET request.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET() {
    return new Response('Profile API data')
}
```

<br><br>

- To solve the conflict move `src/app/dashboard/profile/route.ts` to  `src/app/profile/api/route.ts`
  - Now if you visit `http://localhost:3000/profile` you will see the content of `src/app/dashboard/profile/page.tsx`
  - If you  visit `http://localhost:3000/profile/api` you will see the content of `src/app/dashboard/profile/api/route.ts`



































<br><br>
<br><br>
_____________________________________________________________
_____________________________________________________________
<br><br>
<br><br>



## Handling GET Request
- https://www.youtube.com/watch?v=b3ue9WL5fk8&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=34
- https://marketplace.visualstudio.com/items?itemName=rangav.vscode-thunder-client

- The example below will use memory data and not a databse to keep it simple

<br><br>
<br><br>

- Create `src/app/comments/data.ts`
  - **data.ts is not an next.js file convention name**
```javascript
export const comments = [
    {
        id: 1,
        text: 'This is the first comment'
    },
    {
        id: 2,
        text: 'This is the second comment'
    },
    {
        id: 3,
        text: 'This is the third comment'
    }
]
```

<br><br>

- Create `src/app/comments/route.ts`
  - **data.ts is not an next.js file convention name**
```javascript
import { comments } from './data'

/**
 * Handles the GET request.
 * @returns {Response} The response with the message "Dashboard".
 */
export async function GET() {
    return Response.json(comments)
}
```
- To test open thunderclient ín vs code an make new request




























<br><br>
<br><br>




## Handling POST Request
- https://www.youtube.com/watch?v=pzPS7Fn-8tE&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=36

- `src/app/comments/route.ts`
```
import { comments } from './data'

/**
 * Handles the POST request.
 * @param {Request} req - The request object.
 * @returns {Response} The response.
 */
export async function POST(req: Request) {
    const comment = await req.json()
    const newComment = {
        id: comments.length + 1,
        text: comment.text
    }

    comments.push(newComment)

    return new Response(JSON.stringify(newComment), {
        status: 201,
        headers: {
            'Content-Type': 'application/json'
        }
    })
}
```
- Make POST with payload:
	```javascript
	{
	  "text": "123"
	}
	```
	- Response:
	  ```
	    {
		  "id": 4,
		  "text": "123"
		}
	  ```































<br><br>
<br><br>
__________________________________________________
__________________________________________________
<br><br>
<br><br>


## Dynamic Route Handlers
- https://www.youtube.com/watch?v=TGbC8F0gjC8&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=36


<br><br>

- In order to get the document for a specific id we can do:
  - Create `src/app/comments/[id]/route.ts`:
```javascript
import { comments } from '../data'

/**
 * Handles the GET request.
 * @param {Request} req - The request object.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET(
    req: Request,
    { params } : { params: { id: string }}
) {
    const comment = comments.find(comment => comment.id === Number(params.id))

    return Response.json(comment)
}
```
- GET http://localhost:3000/comments/1
  - Response:
	```javascript
	{"id":1,"text":"This is the first comment"}
	```


















<br><br>
<br><br>




## Handling PATCH Request
- https://www.youtube.com/watch?v=bDbBh7lEamE&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=37

<br><br>

- In order to patch the document for a specific id we can do:
  - Create `src/app/comments/[id]/route.ts`:
```javascript
import { comments } from '../data'

/**
 * Handles the PATCH request.
 * @param {Request} req - The request object.
 * @returns {Response} The response message.
 */
export async function PATCH(
    req: Request,
    { params } : { params: { id: string }}
) {
    const body = await req.json()
    const { text } = body

    const index = comments.findIndex(comment => comment.id === Number(params.id))
 
    comments[index].text = text

    return Response.json(comments[index])
}
```
- PATCH http://localhost:3000/comments/1
	```
	{
	    "text": "123"
	}
	```
	  - Response:
		```javascript
		{
		  "id": 1,
		  "text": "123"
		}
		```






































<br><br>
<br><br>



## Handling DELETE Request
- https://www.youtube.com/watch?v=x3KCt1Oc278&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=38

<br><br>

- In order to delete the document for a specific id we can do:
  - Create `src/app/comments/[id]/route.ts`:
```javascript
import { comments } from '../data'

/**
 * Handles the DELETE request.
 * @param {Request} req - The request object.
 * @returns {Response} The response message.
 */
export async function DELETE(
    req: Request,
    { params } : { params: { id: string }}
) {
    const index = comments.findIndex(comment => comment.id === Number(params.id))
  
    const deletedComment = comments[index]
    comments.splice(index, 1)
 
    return Response.json(deletedComment)
}
```
- DELETE http://localhost:3000/comments/1


































<br><br>
<br><br>
__________________________________________________
__________________________________________________
<br><br>
<br><br>




## URL Query Parameters
- https://www.youtube.com/watch?v=fuxSl-K0oI0&list=PLC3y8-rFHvwjOKd6gdf4QtV1uYNiQnruI&index=40
- E.q. you want to open localhost:3000/comments?query=first

<br><br>

- In order to handle query parameters do:
  - Edit `src/app/comments/route.ts` and add request type `NextRequest`:
```javascript
import { comments } from './data'
import { type NextRequest } from 'next/server'

/**
 * Handles the GET request.
 * @param {Request} req - The request object.
 * @returns {Response} The response.
 */
export async function GET(req: NextRequest) {
    const { searchParams } = req.nextUrl
    const query = searchParams.get('query')

    const filteredComments = query ?
        comments.filter(comment => comment.text.includes(query)) :
        comments

    // status 200 is the default status
    return Response.json(filteredComments)
}
```
- GET localhost:3000/comments?query=first







<br><br>
<br><br>




# Redirects in Route Handlers
- If you would visit http://localhost:3000/comments/4 then you would get a 404 because we only have 3 documents. If you want to redirect the user to a specific page in this you can use:
  - e.g. src/app/comments/[id]/route.ts
```javascript
import { redirect } from 'next/navigation'
import { comments } from '../data'

/**
 * Handles the GET request.
 * @param {Request} req - The request object.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET(
    req: Request,
    { params } : { params: { id: string }}
) {
    if (Number(params.id) > comments.length) {
        redirect('/comments')
    }

    const comment = comments.find(comment => comment.id === Number(params.id))

    return Response.json(comment)
}
```
- In this case the users gets redirected to http://localhost:3000/comments






























<br><br>
<br><br>






# Headers in Route Handlers

<br><br>

## Request header
- If you want to handle request handler e.g. if you call:
  - http://localhost:3000/profile/api
    - HEADER Authorization: Baerer 1234

<br><br>

## method #1
```javascript
import { type NextRequest } from 'next/server'

/**
 * Handles the GET request.
 * @param {NextRequest} request - The request object.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET(request: NextRequest) {
    const requestHeaders = new Headers(request.headers)
    console.log(requestHeaders.get('Authorization'))

    return new Response('Profile API data')
}
```

<br><br>

## method #2
- headers() is read only
```javascript
import { headers } from 'next/headers'

/**
 * Handles the GET request.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET() {
    const headerList = headers()
    console.log(headerList.get('Authorization'))

    return new Response('Profile API data')
}
```


- GET http://localhost:3000/profile/api
  - header Authorization: Bearer 12345


<br><br>


## Response header
```javascript
import { type NextRequest } from 'next/server'

/**
 * Handles the GET request.
 * @param {NextRequest} request - The request object.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET(request: NextRequest) {
    const requestHeaders = new Headers(request.headers)
    console.log(requestHeaders.get('Authorization'))

    return new Response('<h1>Profile API data</h1>', {
    	headers: {
    		'Content-Type': 'text/html'
    	}
    })
}
```


































<br><br>
_______________________________________
_______________________________________
<br><br>

# Cookies in Route Handlers

<br><br>

## Method #1
- You can set Cookies by using Response()
- You can read cookies by using request.cookies.get()
```typescript
import { type NextRequest } from 'next/server'

/**
 * Handles the GET request.
 * @param {NextRequest} request - The request object.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET(request: NextRequest) {
    const theme = request.cookies.get('theme')
    console.log(theme) // { name: 'theme', value: 'dark' }

    return new Response('<h1>Profile API data</h1>', {
    	headers: {
    	    'Content-Type': 'text/html',
            'Set-Cookie': 'theme=dark'
    	}
    })
}
```
  - Make GET 127.0.0.1:3000/profile/api and check the Cookies tab

<br><br>

## Method #2 (recommended)
- https://nextjs.org/docs/app/api-reference/functions/cookies
- You can set Cookies by using cookies().set()
- You can read cookies by using cookies().get()
```typescript
import { type NextRequest } from 'next/server'
import { cookies } from 'next/headers'

/**
 * Handles the GET request.
 * @param {NextRequest} request - The request object.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET(request: NextRequest) {
    cookies().set('theme', 'dark')

    const theme = cookies().get('theme')
    console.log(theme) // { name: 'theme', value: 'dark', path: '/' }

    return new Response('<h1>Profile API data</h1>', {
    	headers: {
    	    'Content-Type': 'text/html'
    	}
    })
}
```
  - Make GET 127.0.0.1:3000/profile/api and check the Cookies tab



































<br><br>
_______________________________________
_______________________________________
<br><br>


# Caching in Route Handlers
- Route Handlers are cached by default when using the GET method with the Response object in Next.js

- Create /src/app/time/route.ts
```typescript
/**
 * Handles the GET request.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET() {
     const res = JSON.stringify({ time: new Date().toLocaleTimeString() })

     return new Response(res, {
          headers: { 'Content-Type': 'application/json' }
      })
}
```
- In dev mode (npm run dev) when you refresh 127.0.0.1:3000/time you will see that the response time is changing
- In build mode (npm run build && npm run start) when you refresh 127.0.0.1:3000/time you will see that the response time is not changing because it is cached

<br><br>

## How to disable caching?

<br><br>

### Method #1 - dynamic mode in segment config options
```typescript
export const dynamic = 'force-dynamic';

/**
 * Handles the GET request.
 * @returns {Response} The response with the message "Profile API data".
 */
export async function GET() {
     const res = JSON.stringify({ time: new Date().toLocaleTimeString() })

     return new Response(res, {
          headers: { 'Content-Type': 'application/json' }
      })
}
```

<br><br>

### Method #2
- Using the Request object with the GET method

<br><br>

### Method #3
- employing dynamic functions like headers() and cookies()

<br><br>

### Method #4
- using any HTTP method other than GET





























<br><br>
<br><br>
____________________________________
____________________________________
<br><br>
<br><br>



# Middleware

<br><br>

## Redirect
- https://nextjs.org/docs/app/api-reference/functions/next-response#redirect

<br><br>

### Method #1
- Create src/middleware.ts
```typescript
import { NextResponse, type NextRequest } from 'next/server'

export function middleware(request: NextRequest) {
    return NextResponse.redirect(new URL('/', request.url))
}

export const config = {
	matcher: '/profile'
}
```
- When you visit 127.0.0.1:3000/profile you will get redirected to 127.0.0.1


<br><br>

### Method #2
- Create src/middleware.ts
```typescript
import { NextResponse, type NextRequest } from 'next/server'

export function middleware(request: NextRequest) {
    if (request.nextUrl.pathname === '/profile') {
        return NextResponse.redirect(new URL('/hello', request.url))
    }
}
```
- When you visit 127.0.0.1:3000/profile you will get redirected to 127.0.0.1/hello







<br><br>
<br><br>


## Rewrite
- https://nextjs.org/docs/app/api-reference/functions/next-response#rewrite
- Produce a response that rewrites (proxies) the given URL while preserving the original URL.

<br><br>

- Create src/middleware.ts
```typescript
import { NextResponse, type NextRequest } from 'next/server'

export function middleware(request: NextRequest) {
    if (request.nextUrl.pathname === '/profile') {
        return NextResponse.redirect(new URL('/time', request.url))
    }
}
```
- When you visit 127.0.0.1:3000/profile you will get redirected to 127.0.0.1/profile but the content of src/app/time/route.ts will be displayed









<br><br>
<br><br>

## Cookies
- Create src/middleware.ts
```typescript
import { NextResponse, type NextRequest } from 'next/server'

export function middleware(request: NextRequest) {
    const response = NextResponse.next()

    const themePreference = request.cookies.get('theme')

    if (!themePreference) {
    	console.log('Cookie not found..')
        response.cookies.set('theme', 'dark')
    }

    return response
}
```
  - When you visit e.g. 127.0.0.1:3000/profile you will see in dev tools > Application > Cookies that the cookie will be set. When you change the value there and then refresh the page you will notice that the cookie value will not change again because of the condition






<br><br>
<br><br>

## Headers
- Create src/middleware.ts
```typescript
import { NextResponse, type NextRequest } from 'next/server'

export function middleware(request: NextRequest) {
    const response = NextResponse.next()
    response.headers.set('custom-header', 'custom-value')
    return response
}
```
- When you visit e.g. 127.0.0.1:3000/profile you will see in dev tools > Network the Response Header `Custom-Header: custom-value`






























<br><br>
<br><br>
___________________________
___________________________
<br><br>
<br><br>


# Rendering
- Rendering is the process that transforms the code you write into user interfaces
- In Next.js, choosing the right time and place to do this rendering is vital for building a performant application
- CSS, SSR and RSCs


<br><br>

<br><br>
<br><br>

## The evolution of React Rendering
- Client-side Rendering (CSR) -> Server-side Rendering (SSR) -> Suspense for SSR -> React Server Components (RSC)











<br><br>
<br><br>

### Client-side Rendering (CSR)
- Client will send Request to server
  - Server returns HTML + JS reference
  ```
  <div id="root"></div>
  <script type="text/javascript" src="/static/js/bundle.js"></script>
  ```
    - The bundle.js contains everything you need to run. Including the react library itself and your application code
      - It is downloaded when the HTML file is parsed
        - The downloaded JS Code then generates the HTML and inserts it into the DOM of the root div

- This method of rendering, where the component code is tranformed into a juser interface directly withing the browser (the client), is known as client-side rendering (CSR)

- CSR quickly became the standard for single page applications (SPA), with widespread adoption


<br><br>
<br><br>

### Drawbacks of CSR

<br><br>

#### SEO
- Generating HTML that mainly contains a single div tag is not optimal for SEO, as it provides little content for search engines to index
  - If there are nested js file which will be rendered and it will not happen fast enough then the crawler may not be able to index 

<br><br>

#### Performance
- Having the browser (the client) handle all the work, such as fetching data, computing the UI, and making the HTML interactive can slow things down. Users might see a blank screen or a loading spinner while the page loads
- Each new feature added to the application increases the size of the Js bundle, prolonging the wait for users to see the UI

















<br><br>
<br><br>

<br><br>
<br><br>


## Server-side Rendering (SSR)
- Client sends request to server
  - Server generates HTML and returns full HTML + JS reference to client

- It significantly improves SEO because search engines can easily index the server-rendered content

- Users can immediately see the page HTML content instead of a blank screen or loading timer


<br><br>
<br><br>

### Hydration
- The full interactive of the page is on hold until the javascript bundle comprising react itself along with your application specific code has been completely downloaded and executed by the browser
  - This important phase known as hydration is where the static HTML page initially served by the server is brought to life

- During hydration, React takes control in the browser, reconstructuting the component tree in memory based on the static HTML that was served

- It carefully plan the placement of interactive elements within this tree. Then, React proceeds to bind the necessary Javascript logic to these elements

- This involves initializing the application state, attaching event handlers for actions such as clicks and mouseovers and seeting up any other dynamic functionalities required for a fully interactive user experience




<br><br>
<br><br>

### Server-side Solutions

<br><br>

#### Static Site Generation (SSG)
- SSG occurs at build time, when the application is deployed on the server. This results in pages that are already rendered and ready to server. It is ideal for content that doesnt change often, like blog posts

<br><br>

#### Server-Side Generation (SSR)
- SSR renders pages on-demand in response to user requests. It is suitable for personalized content like social media feeds, where the HTML depends on the logged-in user
- SSR was a significant improvement over CSR providing faster initial page loads and better SEO




<br><br>
<br><br>

## Drawbacks of SSR
- You have to fetch everything before you can show anything
  - Components cannot start rendering and then pause or wait while data is still being loaded
  - If a component needs to fetch data from a database or another source (e.g. an API), this fetching must be completed before the server can begin rendering the page
  - This can delay the servers response time to the browser, as the server must finish collecting all necessary data before any part of the page can be sent to client

- You have to load everything before you can hydrate anything
  - For successful hydration, where react adds interactivity to the server-rendered HTML, the component tree in the browser must exactly match the server-generated component tree
    - This means that all the javascript for the components must be loaded on the client before you can start hydrating any of them

- You have to hydrate everything before you can interact with anything
  - React hydrated the component tree in a single pass, meaning once it starts hydrating, it wont stop until it is finished with the entire tree
    - As consequence, all components must be hydrated before you can interact with any of them

<br><br>

### Drawbacks of SSR - All or Nothing Waterfall
1. Having to load the data for the entire page
2. Load the javascript for the entire page, and
3. hydrate the entire page
- create an "all or nothing" waterfall problem that spans from the server to the client, where each issue must be resolved before moving to the next one

- This is inefficient is some parts of your app are slower than others, as is often the case in real-world apps


































<br><br>
<br><br>

<br><br>
<br><br>


## Suspense SSR Architecture
- Use the <Suspense> component to unlock two major SSR features:
  - 1. HTML streaming on the server
  - 2. Selective hydration on the client

<br><br>

### HTML streaming on the Server
- You do not have to fetch everything before you can show anything

- If a particular section delays the initial HTML, it can seamlessly integrated into the stream later

- This is the essence of how Suspense facilitates server-side HTML streaming


<br><br>
<br><br>

### The other challenger
- Until the javascript for the main section is loaded, client-side app hydration cannot start
  - And if the javascript bundle for the main section is large, this could significantly delay the process


<br><br>
<br><br>

#### Code splitting
- Code splitting allows you to mark specific code segments as not immediately necessary for loading, signalling your bundler to segregate them into seperate `<script>` tags

- Using `React.lazy` for code splitting enables you to seperate the main sections code from the primary javascript bundle
  - The javascript containing React and the code for the entire application, excluding the main section, can now be downloaded independently by the client, without having to wait for the main sections code






<br><br>
<br><br>

### Selective Hydration on the Client
- This process is managed automatically by React

- Selective hydration offers a solution to the issue `The necessity to hydrate everything to interact with anything`

- By wrapping the main section within `<Suspense>`, you've indicated to React that it should not prevent the rest of the page from not just streaming but also from hydrating
  - This feature, called selective hydration allows for the hydration of sections as they become available, before the rest of the HTML and the Javascript code are fully downloaded

- Thanks to Selective hydration, a heavy piece of JS does not prevent the rest of the page from becoming interactive

- React begins hydrating as soon as possible, enabling interactions with elements like the header and side navigation without waiting for the main content to be hydrated

- In scenarios where multiple components are awaiting hydration, React prioritizes hydration based on user interactions





<br><br>
<br><br>

### Drawbacks of Suspense for SSR
- Even though javascript code is streamed to the browser asynchronously, eventually, the entire code for a web page must be downloaded by the user
	- As applications add more featues, the amount of code users need to download also grows. This leads to an important question:
	  - should users really have to download so much data?

- The current approach requires that all React components undergo hydration on the client-side, irrespective of their actual need for interactivity
  - This process can inefficiently spend resources and extend the loading times and time to interactivity for users, as their devices need to process and render components that might not even require client-side interaction
  - This leads to an important question:
    - Should all components be hydrated, even those that do not need interactivity?

- In spite of servers superior capacity for handling intensive processing tasks, the bulk of javascript execution still takes place on the users device
  - This can slow down the performance, especially on devices that are not very powerful
    - This leads to an important question:
      - should so much of the work be done on the users device?
     



























<br><br>
<br><br>
<br><br>
<br><br>

# React Server Components (RSC)
- The app router in Next.js is built around the RSC architecture

- This approach aims to leverage the strengths of both server and client environments, optimzing for efficiency, load times and interactivity

- The architecture introduces a dual-component model
  - Client Components
  - Server Components

  This disctinction is not based on the functionality of the components but rather on where they execute and the specific environments they are designed to interact with


- take charge of data fetching and static rendering, while Client Components are tasked with rendering the interactive elements of the application

- The bottom line is that the RSC architecture enabled React applications to leverage the best aspects of both server and client rendering, all while using a single language, a single framework and a cohesive set of API's







<br><br>
<br><br>

## Client Components
- are the familiar React components we've been using

- They are typically rendered on the client-side (CSR) but, they can also be rendered to HTML on the server (SSR), allowing users to immediately see the page's HTML content rather than a blank screen

- Components that primarily run on the client but can (and should) also be executed once on the server as an optimization strategy

- have access to the client environment, such as the browser, allowing them to use state, effetcs, and event listeners to handle interactivity and also access browser-exclusive API's like geolocation or localStorage, allowing you to build UI for specfic use cases

- In fact, the term "Client Component" does not signify anything new. It simply helps differentiate these components from the newly introduced Server Components











<br><br>
<br><br>

## Server Components
- represent a new type of React component specifically designed to operate exclusively on the server

- Unlike client components, their code stays on the server and is never downloaded to the client

- this design choice offers multiple benefits to React applications



<br><br>
<br><br>

## Benefits of Server Components

<br><br>

### Reduced Bundle Sizes
- Server Components do not send code to the client, allowing large dependencies to remain server-side
- This benefits users with slower internet or less capable devices by elimnating the need to download, parse and execute javascript for these components
- Additionally it removed the hydration step, speeding up app loading and interaction


<br><br>

### Direct Access to Server-side Resources
- By having direct access to Server-side Resources like databases or file systems, Server Components enable efficient data fetching and rendering without needing additional client-side processing
- Leveraging the servers computational power and proximity to data sources, they manage compute-intensive rendering tasks and send only interactive pieces of code to the client


<br><br>

### Enhanced Security
- Server Components exclusive server-side execution enhances security by keeping sensitive data and logic, including tokens and API keys, away from the client-side

<br><br>

### Improved Data Fetching
- Server Components enhance data fetching efficiency

 - typically, when fetching data on the client-side using useEffect, a child component cannot begin loading its data until the parent component has finished loading its own
    - This sequential fetching of data often leads to poor performance
    - The main issue is not the round trips themselves, but that these round trips are made from the client to the server
      - Server Components enable applications to shift these sequential round trips to server side
        - By moving this logic to the server, request latency is reduced and overall performance is improved, elimating client-server "waterfalls"


<br><br>

### Caching
- Rendering on the server enables caching of the results, which can be reused in subsequent requests and accross different users
  - This approach can significantly improve performance and reduce costs by minimizing the amount of rendering and data fetching required for each request


<br><br>

### Faster Initial Page Load and First Contentful Paint
- Sixth, Initial Page Load and First Contentful Paint (FCP) are significantly improved with Server Components
- By generating HTML on the server, pages become immediately visible to users without delay of download, parsing, and executing javascript


<br><br>

### Improved SEO
- Regarding Search Engine Optimization (SEO), the server-rendered HTML is fully accessible to search engine bots, enhancing the indexability of your pages


<br><br>

### Efficient Streaming
- Server Components allows the rendering process to be divided into mangeable chunks, which are then streamed to the client as soon as they are ready
  - This approach allows users to start seeing parts of the page earlier, eliminating the need to wait for the entire page to finish rendering on the server



































<br><br>
<br><br>
_________________________________________________________________
_________________________________________________________________
<br><br>
<br><br>



# Server Components
- By default, every component in a Next.js app is considered a server component
- Including the root layout (src/app/layout.tsx) and root page (src/app/page.tsx)

1. Create new project
```shell
npx create-next-app@latest rendering-demo
```

2. Create Server Component `src/appp/about/page.tsx`
```javascript
export default function AboutPage() {
  console.log('Test')

  return (
    <>
      <h1>About page</h1>
    </>
  );
}
```
- You can verify it by using console.log()
  - You will see that the log is only in your terminal from your app and not client-side


<br><br>

Imagine you would try to use useState() inside of this server component which is only allowed in client components you would get the error **"You're importing a component that needs useState. It only works in a Client Component but none of its parents are marked with "use client", so they're Server Components by default"**
```javascript
// https://react.dev/reference/react/useState
import { useState } from 'react'

export default function AboutPage() {
  const [name, setName] = useState('')

  console.log('Test')

  return (
    <>
      <h1>About page</h1>
    </>
  );
}
```










<br><br>
<br><br>


# Client Components

1. Create client component `dashboard/page.tsx`
```typescript
'use client'

import { useState } from 'react'

export default function DashboardPage() {
  console.log('DashboardPage()')

  const [name, setName] = useState('')

  return (
    <div>
      <h1>Dashboard</h1>
      <input value={name} onChange={(e) => setName(e.target.value)} />
      <p>Hello, {name}!</p>
    </div>
  );
}
```
- `'use client'` will be set on the top to define the client component

2. Add to `src/app/page.tsx` at the top:
```typescript
import Link from 'next/link'
```

Then add to the main component:
```html
<Link href="/dashboard">Dashboard</Link>
```

Now open:
- http://localhost:3000
  - Then click on the dashboard link and check the browser console. **You'll see that the console.log() from your dashboard page.tsx will be logged now twice**. But the log will not be inside your app terminal.
    - This is because of reacts strict mode. If you refresh now the browser at `http://localhost:3000/dashboard` you'll see that the console.log() from your dashboard page.tsx will be logged now **again** twice in your browser console. **But aswell one time in your app terminal**
      - Client Components are primeraly execute on the client-side and have access to browser API's but they are also pre-rendered once on the server to allow the user to immediately see the page HTML content rather than a blank screen.
        - **Even if it is may confusing this means a client component executes once on the server and then on the client**































<br><br>
<br><br>
_________________________________________________
_________________________________________________

<br><br>
<br><br>







# React Server Component (RSC) Rendering Lifecycle
- It is important to consider three elements:
  - Client side: Your browser,
  - Server side: Next.js & React


<br><br>

## Initial Loading sequence
- Client Request -> Next.js App Router -> Matches URL to a server component
  - Next.js instructs react to render server component -> React renders the server component and any child components that are also server components by converting them into a special JSON format known as the RSC payload
    - If you visit any page.tsx file you can see this JSON firmat in the Response Tab
    - During this rendering if any server components suspends reacts pauses rendering of that subtree and sends a placeholder value instead. Meanwhile client components are prepared with instructions for later in the life cycle. Next.js uses the RSC payload which includes the client component instructions to generate HTML on the server. -> This HTML is streamed to your browser to immediately show a fast non-interactive preview of the route (**non-interactive UI**). Alongside Next.js streams the RSC payload as react render each unit of the UI
      - In the browser Next.js processes the streamed react reponse. React uses the RSC payload and cient component instructions to progressively render the UI
        - Once all the components and the server components output has been loaded and  presented to the user (**Final UI**). 
          - The user client components undergo hydration  transforming our app from a static display into an interactive experience. This is the initial loading sequence (**Interactive UI**)


<br><br>

## Update Sequence
- Important for refreshing parts of the app

- The browser requests a re-fetch of a specific UI such as a full route -> Next.js processes the request and matches it to the requested server component
  - Next.js instructs react to render the component tree -> React renders the components similar the initial loading. But unlike the initial sequence there is no HTML generation for updated sequence. Next.js progressively streams the response data back to the client
    - On recieving the streamed response next.js triggers a re-render of the route using the new output. React reconciles or merges the new rendered output with the existing components on screen since the uI description is a special JSON format and not HTML react can update the DOM while preserving crucial UI updated such as focus or input values



















<br><br>
<br><br>


# Server Render Strategies
- Static rendering
- Dynamic rendering
- Streaming


<br><br>
<br><br>


## Static rendering
- Is a server rendering strategy where we generate HTML pages at the time of building our application
  - This approach allows the page to be built once, cached by a CDN and served to the client almost instantly
  - This optimization also enables you to share the result of the rendering work among different users, resulting in a signifcant performance boost for your application

- Is particulary useful for blog pages, e-commerce product pages, documentation and marketing pages

<br><br>
<br><br>

### How to statically render?
- Static rendering is the default rendering strategy in app router
  - All routes are automaticallyprepared at build time without additional setup


<br><br>
<br><br>

## Production Server vs Dev Server
- For production, an optimized build is created once and you deploy that build
  - For production builds, a page will be pre-rendered once when we run the build command

- A development server, on the other hand, focuses on the developer experience
  - We can not affort to build our app once, make changes, rebuild and so on
  - In development mode, a page will be pre-rendered for every request



<br><br>
<br><br>

### Understand what happens in `npm run build`
1. Delete .next folder

<br><br>

2. Create `src/app/about/page.tsx`
```javascript
import { cookies } from "next/headers";

export default function AboutPage() {
  const cookieStore = cookies();
  const theme = cookieStore.get("theme");
  console.log(theme);
  return (
    <>
      <h1>About page {new Date().toLocaleTimeString()}</h1>
    </>
  );
}
```

<br><br>

3. Run `npm run build`
- The output folder for the build will be the .next folder

The logs in terminal will look like this:
```
npm run build 


> rendering-demo@0.1.0 build
> next build

   ▲ Next.js 14.1.0

   Creating an optimized production build ...
 ✓ Compiled successfully
 ✓ Linting and checking validity of types    
 ✓ Collecting page data    
 ✓ Generating static pages (8/8) 
 ✓ Collecting build traces    
 ✓ Finalizing page optimization    

Route (app)                              Size     First Load JS
┌ ○ /                                    11.3 kB        95.4 kB
├ ○ /_not-found                          882 B            85 kB
├ λ /about                               140 B          84.3 kB
├ ○ /dashboard                           345 B          84.5 kB
└ ○ /product-detail                      140 B          84.3 kB
+ First Load JS shared by all            84.1 kB
  ├ chunks/69-9c3c64001cadfd4c.js        28.9 kB
  ├ chunks/fd9d1056-534a3af521b04580.js  53.4 kB
  └ other shared chunks (total)          1.87 kB


○  (Static)   prerendered as static content
λ  (Dynamic)  server-rendered on demand using Node.js
```
- It shows informations about each route in our app


<br><br>
<br><br>

#### Size
- You could three columns there:
    - Route (app)

    - Size
      - Refers to the size of the assets downloaded when navigating to the corresponding route client side in the browser

    - First Load JS
      - Refers to the size of the assets downloaded when loading the page from the server
      - The First Load JS shared by all includes the CSS from global.css, some runtime code, framework code, node modules, vendor code (e.g. react) and some code related to the routes and components in our app
        - **This means e.g. for the /about route the size of 11.3kb + `First Load JS shared by all` with 84.1kb will be added together = 95.4kb**


<br><br>
<br><br>

#### Legend
- Hollow Circle ○
  - Indicates static rendering where the route is automatically pre-rendered at build time as static HTML content

- Lambda Symbol λ
  - Indicated dynamic rendering - server-rendered on demand using Node.js










<br><br>
<br><br>

#### .next folder
- `npm run build` will save the output in the .next folder which contains various files and folders essential for serving our application to incoming requests from the browser

<br><br>

##### server folder
- We have an app folder corresponding to the app router
    - Our build info shows that the root page is a static HTML page (hollow circle)
      - The same can we found in `.next/server/app/index.html`. The same is for the outer routes about.html and so on
      - **Remember even client components are pre-rendered as an optimization step and that is the reason we see the client component HTML**

    - Each route as RSC payload e.g. `.next/server/app/about.rsc`
      - It is a special JSON format generated by react for each route. It is a compact string representation of the virtual DOM. It includes abbreviations, internal references and encoded special meaning
        - For a server component the payload includes the rendered result of the server component like the H1 tag with the text about page (The page.tsx from our component)
        - For a client component the payload includes placeholders or instructions where client components should be rendered along with references to their javascript files







<br><br>
<br><br>

4. Execute `npm run start` to serve our application. 
- Will run our application on `localhost:3000`
  - Check the network tab and click on `empty cache` and `hard reload` (Same to open it again new in incognito mode)
    - As you can see the preview of the HTML page and in the Response Tab you can see the HTML code.

    - Check e.g. the rsc file for dashboard `dashboard?_rsc`
      - This is essential for building the UI on the client side when we navigate to /dashboard using the link.  
        - The component code for the dashboard represented by `/page-xxxxxxx.js` and has also been downloaded
          - If you click on thedashboard link you will notice that the route will instantly work without loading. This is because it is rendered without the need to download any additional resources from the server. It already includes everything for client side navigation





<br><br>
<br><br>


#### Prefetching
- Prefetching is a technique used to preload a route in the background before the user navigates to it
- Routes are automatically prefetched as they become visible in the users viewport, either when the page first load or as it comes into view through scrolling 
- For static routes, the entire route is prefetched and cached by default
  - When we load the homepage, Next.js prefetches the About and Dashboard routes, keeping them ready for instant navigation (If you include a link)
    - dashboard.html will be served when you would open `localhost:3000/dashboard`
      - When you refresh the page you will notice that the initial loading time takes longer than all other after them this is because of the caching













































<br><br>
<br><br>
<br><br>
<br><br>


## Dynamic rendering
- Is a server rendering strategy where routes are rendered for each user at request time
- It is useful when a route has data that is personalized to the user or contains information that can only be known at request time, such as cookies or the URL's search parameters
  - e.g. news website, personalized e-commerce pages or social media feeds are some examples

<br><br>
<br><br>

### How to dynamically render
- During rendering, if a dynamic function is discovered, Next.js will switch to dynamically rendering the whole route
- In Next.js, these dynamic functions are: cookies(), headers and searchParams
  - Using any of the will opt the whole route into dynamic rendering at request time

<br><br>

1. Add to `src/app/about/page.tsx`
```typescript
import { cookies } from "next/headers";

export default function AboutPage() {
  const cookieStore = cookies();

  const theme = cookieStore.get("theme");
  console.log(theme);

  return (
    <>
      <h1>About page {new Date().toLocaleTimeString()}</h1>
    </>
  );
}
```

<br><br>

2. Delete `.next` folder

<br><br>

3. Run `npm run build`
- As related to the explaining in Static Rendering we will have the output with the sizes where the about route will have a lambda symbol λ
- In contrast to static rendering, there will be nothing rendered at build time. So there is file: `.next/server/app/about.html`

<br><br>

4. Run `npm run start`
- If you refresh now `localhost:3000/about` the page is pre-remdered and you can see the console.log statement in the terminal
  - In the network tab we can see the preview as well as the response which contains the HTML. Refreshing `localhost:3000/about` will render the latest time `new Date().toLocaleTimeString()`.
    - But the HTML file is still not generated in `.next/server/app` since a new page is built for every request there is no need to generate a page
   



































<br><br>
<br><br>
<br><br>
<br><br>




## Streaming
- Is a strategy that allows for progressive UI rendering from server
  - Work is divided into chunks and streamed to the client as soon as it is ready
    - This enables users to see parts of the page immediately, before the entire content has finished rendering

- Significantly improves both the initial page loading performance and the rendering of UI elements that rely on slower data fetches, which would otherwhise block the rendering of the entire route. Similiar to Suspense for SSR
  - Streaming is integrated into the Next.js App router by default

<br><br>

1. Create `src/app/product-detail/page.tsx`
```typescript
import { Suspense } from "react";

import { Product } from "@/components/product";
import { Reviews } from "@/components/reviews";

export default function ProductDetailPage() {
  return (
    <div>
      <h1>Product detail page</h1>
      <Product />
      <Reviews />
    </div>
  );
}
```

<br><br>

`src/app/components/product.tsx`
```typescript
export const Product = async () => {
  await new Promise((resolve) => setTimeout(resolve, 2000));
  return <div>Product</div>;
}
```

<br><br>

`src/app/components/reviews.tsx`
```typescript
export const Reviews = async () => {
  await new Promise((resolve) => setTimeout(resolve, 4000));
  return <div>Reviews</div>;
}
```

<br><br>

We are intentionally delaying the rendering of the product component by 2 seconds and the reviews component by 4 seconds. This simulates the time taken to fetch data

<br><br>

2. Run `npm run dev`

<br><br>

3. Open `localhost:3000/product-detail`
- You will notice that the page will take time to render the H1 tag along with the two components. When you refresh again you will see in the network tab the `waiting for server response` with 4+ seconds. Indicating that the data for the entire page is fetched before sending the response 

<br><br>

4. Lets enhance this with the streaming strategy supported in the app router by adding to `src/app/product-detail/page.tsx`. All we need to do is import the suspense component and wrap the other componse with suspense and next.js handles everything:
```typescript
import { Suspense } from "react";

import { Product } from "@/components/product";
import { Reviews } from "@/components/reviews";

export default function ProductDetailPage() {
  return (
    <div>
      <h1>Product detail page</h1>
      <Suspense fallback={<p>Loading product details...</p>}>
        <Product />
      </Suspense>
      <Suspense fallback={<p>Loading reviews...</p>}>
        <Reviews />
      </Suspense>
    </div>
  );
}
```

5. Reload `localhost:3000/product-detail` and now we immediately see the H1 and the fallbacks. The fallbacks will be replace with the content of the components until they are done with the timeout
