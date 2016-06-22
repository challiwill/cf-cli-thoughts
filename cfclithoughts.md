##How backwards compatibility makes a better user experience impossible
Looking at github.com/cloudfoundry-attic/CF-CLI-Improvements we have work from designers
to make the command structure better/more user friendly/focused on what users actually
mostly use. We cannot move in this direction while keeping indefinite backwards compatibility
because it changes the structure of commands. We need an opportunity to make breaking changes.
When we experiemented with rewriting from scratch we ended up with the same flat structure
because our current commands demand that. This creates disorganized code, reduces how code
can be reused between commands, and makes for a challenging user experience (Aakash: "doesn't
everyone just grep help for what they need?"). We should have tiered commands like bosh.

##General help improvements
The whole help should be visible on one screen. It's ridiculous to have to scroll so much to
find what you're looking for. All commands top level commands should be listed on one page.

##Thoughts on `object verb` command structure
This sounded great to me at first, but after a conversation with Dmitriy about BOSH moving
away from `object verb` I had some more thoughts. Nested commands would end up with strange
aliases: `cf push app` would become `cf p a`. It also eliminates the possibility for auto-
completion. Perhaps `object-verb` or `verb-object` would in fact be better.

##It would be good to track UX issues in a document somewhere

