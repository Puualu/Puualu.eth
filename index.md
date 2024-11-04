---
layout: default
---

# Global change begins within..

This is the official site for puualu.eth, where you can find project updates, learn how to participate in important work.  Payments and Donations support local movements happening.

## Support Us
Your support is appreciated! Donations can be sent directly to [puualu.eth](https://etherscan.io/enslookup?q=puualu.eth).

## NFT Gallery
Check out some of the latest NFTs in the gallery.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>NFT Gallery</title>
    <style>
        .nft-gallery { display: flex; flex-wrap: wrap; }
        .nft-item { margin: 10px; width: 200px; }
        .nft-item img { width: 100%; height: auto; }
    </style>
</head>
<body>
    <h1>NFT Gallery</h1>
    <div class="nft-gallery" id="nftGallery"></div>
    <script src="gallery.js"></script>
</body>
</html>

### Header 3

```jsasync function fetchNFTs() {
    const nftGallery = document.getElementById("nftGallery");

    try {
        // Fetch NFTs from OpenSea using the ENS domain (replace with your own API key if required)
        const response = await fetch(`https://api.opensea.io/api/v1/assets?owner=puualu.eth&order_direction=desc&offset=0&limit=10`);
        const data = await response.json();

        data.assets.forEach(asset => {
            const nftItem = document.createElement("div");
            nftItem.className = "nft-item";
            nftItem.innerHTML = `
                <img src="${asset.image_url}" alt="${asset.name}">
                <h3>${asset.name}</h3>
                <p>${asset.description || 'No description available'}</p>
                <a href="${asset.permalink}" target="_blank">View on OpenSea</a>
            `;
            nftGallery.appendChild(nftItem);
        });
    } catch (error) {
        console.error("Failed to load NFTs:", error);
        nftGallery.innerHTML = "<p>Failed to load NFTs. Please try again later.</p>";
    }
}

// Fetch NFTs on page load
fetchNFTs();


```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
