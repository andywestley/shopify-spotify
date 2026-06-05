# Shopify Spotify Widgets

A lightweight, modern, and flexible integration for embedding Spotify players (tracks and playlists) directly into your Shopify theme (e.g., Dawn) using native Shopify Metafields.

This integration allows store owners to tie products to specific songs (using track players) and collections to specific playlists (using playlist embeds).

---

## Features

- **Flexible Input Parsing**: Accepts full Spotify sharing URLs, URI strings, or clean Spotify IDs.
- **Dynamic Collection Playlists**: Embeds Spotify playlists on collection templates with custom fallbacks.
- **Theme-Editor Friendly**: Once code is added, placement and styling can be managed 100% via the Shopify Theme Customizer.
- **Polished UX**: Embedded widgets come with elegant hover state micro-animations and drop-shadow styling.

---

## Code Structure

- [snippets/spotify-track-player.liquid](file:///c:/Users/Andrew/Documents/github/shopify-spotify/snippets/spotify-track-player.liquid): Embedded track player for product pages.
- [sections/spotify-collection-playlist.liquid](file:///c:/Users/Andrew/Documents/github/shopify-spotify/sections/spotify-collection-playlist.liquid): Full-width customizable section for collection playlists.

---

## Setup Instructions

### Step 1: Create Metafields in Shopify Admin

1. Go to your **Shopify Admin** > **Settings** > **Custom data**.

#### For Products (Individual Songs)
1. Click **Products** > **Add definition**.
2. Set **Name** to `Spotify Track Identifier`.
3. Set **Namespace and key** to `spotify.track_identifier`.
4. Set **Type** to `Single line text`.
5. Click **Save**.

#### For Collections (Playlists)
1. Click **Collections** > **Add definition**.
2. Set **Name** to `Spotify Playlist Identifier`.
3. Set **Namespace and key** to `spotify.playlist_identifier`.
4. Set **Type** to `Single line text`.
5. Click **Save**.

---

### Step 2: Install Files to Theme

1. Copy [spotify-track-player.liquid](file:///c:/Users/Andrew/Documents/github/shopify-spotify/snippets/spotify-track-player.liquid) into your theme's `snippets/` folder.
2. Copy [spotify-collection-playlist.liquid](file:///c:/Users/Andrew/Documents/github/shopify-spotify/sections/spotify-collection-playlist.liquid) into your theme's `sections/` folder.

---

### Step 3: Embed Widgets via Theme Editor

#### Add Song Player to Product Pages
1. Go to **Online Store** > **Themes** and click **Customize** on your theme.
2. Select **Products** > **Default product** in the top dropdown.
3. Under the **Product information** section, click **Add block** and select **Custom Liquid**.
4. Paste the following snippet:
   ```liquid
   {% render 'spotify-track-player', product: product, size: 'compact' %}
   ```
   *(Change `size: 'compact'` to `size: 'large'` to show the full album artwork).*
5. Drag the block to your desired location and click **Save**.

#### Add Playlist Player to Collection Pages
1. In the Theme Customizer top dropdown, select **Collections** > **Default collection**.
2. In the sidebar, click **Add section** and select **Spotify Playlist Embed**.
3. Customize the title, description, heights, and fallback playlist URL (which displays if the collection metafield is empty).
4. Click **Save**.
