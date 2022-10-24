# NetNinja Next.js and Contentful tutorial

## Notes and key learning points

### Tutorial 2 - Contentful Models

- Contentful is a 'headless' CMS - a CMS without front end templates attached
- Still gives us a place to create data - but doesn't push data into a theme, etc
- Just stores the data - can reach out from our website to fetch it
- Create a 'content model' for a recipe / content type
- Then 'Add field' - 'text' - add a title then 'create and configure'
- In the Validation tab - make the field unique as our 'slugs' for routing will be based on the title, so each slug and title must be unique
- For the next field, select 'text' again but call it 'Slug'
- Select appearance as 'Slug' - will take the title field and auto-generate a slug for us
- For the Method select 'Rich Text' which allows formatting of the recipe
- Once completed all fields - save
- To add a recipe go to 'Content'
- To upload images go to 'Media' - add multiple assets
- Check all images and then 'Publish'

### Tutorial 3 - Contentful site build

- Note that Next.sj automatically grabs environment variables and adds them to the process object
- Remember to restart the server after adding environment variables

### Tutorial 5 - Using images from Contentful

- Built in image component that comes with Next.js
- Auto-optimises our image content
- Remember to add width and height properties
- In order to use the Next.js Image component with images from an external domain - have to 'whitelist' that domain
- Need to add `["images.ctfassets.net"]` to the `next.config.js` file
- Note that the Image component facilitates lazy loading of the images

### Tutorial 6 - Styled JSX

- Can add styles into our JSX templates
- Scopes the styles to the relevant component only
- The styles only apply inside the component where we declare the styled JSX

### Tutorial 7 - Generating Paths

- Note that the `createClient()` function is not included within `getStaticProps` in the `[slug.js]` file, as need to use the data in two seperate functions
- If include it in a single function then would only be scoped to that individual function
- Within `getStaticProps` destructure the params property from the context object returned from `getStaticPaths`
