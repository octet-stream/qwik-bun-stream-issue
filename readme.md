# qwik-bun-stream-issue

Reproduction for Qwik City issue with WritableStream in Bun

## Reproduction

1. Clone this repository;
2. Install dependencies via `bun i`;
3. Build the project for production `bun run build`;
4. Start the app via `bun run serve`;
5. Open [http://localhost:3000](http://localhost:3000) in your browser;

After the main page shows up, look at the terminal and you'll see following error:

```
$ bun server/entry.bun.js
Server started: http://localhost:3000/
636 |     } finally {
637 |       await stream.ready;
638 |       await stream.close();
639 |       await pipe;
640 |     }
641 |     await writableStream.close();
                          ^
TypeError: WritableStream.close method can only be used on non locked WritableStream
      at writableStreamCloseForBindings (:1:21)
      at /Users/octetstream/projects/qwik-bun-stream-issue/server/entry.bun.js:641:11
```
