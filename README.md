# hypertext.dev

A Hugo blog deployed to GitHub Pages by GitHub Actions.

## Writing

    hugo new posts/my-post-title.md          # plain post
    hugo new posts/my-post-title/index.md    # post with its own folder for images/video

Set `draft: false` when it's ready. Add `link: "https://..."` to the front matter to make a link post.

Preview locally with `hugo server -D` (the `-D` shows drafts), then open http://localhost:1313.

Publish: `git add . && git commit -m "New post" && git push`

## Media

- Image: put `photo.jpg` in the post's folder, then `![Alt text](photo.jpg "Optional caption")`
- YouTube: `{{< youtube VIDEO_ID >}}`
- Vimeo: `{{< vimeo VIDEO_ID >}}`
- Small MP4 in the post folder: `{{< video src="clip.mp4" caption="Optional" >}}`

## Changing the look

All styling is in `assets/css/style.css`; colors are the variables at the top.
