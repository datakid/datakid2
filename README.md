# Bayan Alkharji inventory form

Entry form for units sold and prices, by pharmacy and month. It submits to a remote endpoint.

## What it does

- Identifies the pharmacy by ID, such as `a21`, or by class, region and pharmacy.
- Takes a month from 1 to 12 and a list of items, each with units sold and a price. Item names are searched with Fuse.js.
- Shows an undo toast after removals.
- Saves the form as you work and restores it on the next visit.
- Submits the items as JSON in a single POST. The page reports an offline connection or a likely duplicate submission for the same pharmacy, month and class.

## What it does not do

- It has no offline queue. When the connection fails, the form stays on screen and the error is shown.
- It does not read back what was submitted.
- The pharmacy list and the endpoint address are fixed in `index.html`.
- It keeps one draft in `localStorage` under `pharmacyAppState`.

## Network and install

Calls a Cloudflare Worker to submit items, loads Fuse.js 6.6.2 from cdnjs and loads Google Fonts. It makes no other requests. Not installable; no service worker.

## Built with

One HTML file, with no build step and no framework. Fuse.js 6.6.2 provides the item search.

## Run locally

Serve the folder with any static file server. Submitting needs a connection to the endpoint.
