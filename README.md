# PDFtoChat

## Todos v0.5

- [x] Base functionality working w/ pinecone and openai
- [x] Add upload component for pdfs
- [x] Figure out how to acccept remote pdfs
- [x] Move ingest-data file into an API route
- [x] Add logic to run the ingest-data file with the userID + timestamp after user has uploaded a file
- [x] Don't show the chat unless the ingesting was successful, add loading state for ingesting
- [x] In the prompt, add giving back the answer as HTML or markdown to format it well
- [x] Figure out how to use namespaces so folks can search their own PDFs

## Todos v0.5

- [x] Add a PDF viewer
- [x] Migrate to the app router
- [x] Clean up files
- [x] Have PDF viewer and chat side by side
- [x] Add auth with Clerk
- [x] Make the correct pdf show up in the viewer by adding Postgres DB (docId, userId, pdfUrl, createdAt)
- [x] Restrict users to 3 PDFs per account
- [x] Make UI better overall
- [x] Implement the new UI for the document page

## Todos v1

- [ ] Stream data back using the Vercel AI SDK
- [ ] Add loading UI for ingesting data
- [ ] Move away from that APAC region on pinecone, upgrade acc
- [ ] Implement the landing page UI
- [ ] Implement design changes on pdf page + fix responsiveness
- [ ] Add SEO metadata in layout.tsx

## Todos v1.5

- [ ] Move to latest Upload library
- [ ] Tell folks to compress PDFs if they're beyond 10MB or accept more
- [ ] Add trash icon for folks to delete PDFs and implement delete functionality
- [ ] Add sources with a page number
- [ ] Use the uploader from https://zoo.replicate.dev/
- [ ] Use LLM Report for OpenAI observability
- [ ] Migrate all CSS modules to tailwind

## Todos v2

- [ ] Add an option to get answers as lists or paragraphs
- [ ] Error handling
- [ ] Add rate limiting for uploads
- [ ] Replace images from chat with something better
- [ ] Make it detect handdrawn images: https://replicate.com/meta/nougat
- [ ] Use Vercel KV for caching
- [ ] Use Vercel Postgres w/ pgvector instead of Pinecone

**General errors**

- Make sure you're running the latest Node version. Run `node -v`
- Try a different PDF or convert your PDF to text first. It's possible your PDF is corrupted, scanned, or requires OCR to convert to text.
- `Console.log` the `env` variables and make sure they are exposed.
- Make sure you're using the same versions of LangChain and Pinecone as this repo.
- Check that you've created an `.env` file that contains your valid (and working) API keys, environment and index name.
- If you change `modelName` in `OpenAI`, make sure you have access to the api for the appropriate model.
- Make sure you have enough OpenAI credits and a valid card on your billings account.
- Check that you don't have multiple OPENAPI keys in your global environment. If you do, the local `env` file from the project will be overwritten by systems `env` variable.
- Try to hard code your API keys into the `process.env` variables if there are still issues.

**Pinecone errors**

- Make sure your pinecone dashboard `environment` and `index` matches the one in the `pinecone.ts` and `.env` files.
- Check that you've set the vector dimensions to `1536`.
- Make sure your pinecone namespace is in lowercase.
- Pinecone indexes of users on the Starter(free) plan are deleted after 7 days of inactivity. To prevent this, send an API request to Pinecone to reset the counter before 7 days.
- Retry from scratch with a new Pinecone project, index, and cloned repo.

## Credit

- Mako for the original repo
