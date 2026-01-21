# Video Carousel Integration Guide

## Installation Instructions

### Step 1: Insert the Carousel into index.html

**Location**: Insert after the featured products section (around line 238)

**Find this section in index.html:**
```html
                    </div>

                    <!-- Main Headline -->
                    <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold mb-8 tracking-tight leading-tight">
```

**Insert the carousel component RIGHT BEFORE the "Main Headline" section**

1. Open `index.html`
2. Find line 238-240 (the closing `</div>` after featured products grid)
3. Copy the entire content from `video-carousel-section.html`
4. Paste it between the closing products `</div>` and the "Main Headline" `<h2>`

### Step 2: Verify Integration

After inserting, the structure should be:
```
Featured Products Grid
    </div>  <!-- closes products grid -->

<!-- VIDEO CAROUSEL SECTION -->
[Your new carousel code here]
<!-- END VIDEO CAROUSEL -->

<!-- Main Headline -->
<h2 class="text-3xl sm:text-4xl...">
```

## Features Included

✅ **Responsive Design**
- Desktop: Full-width video player with side navigation
- Tablet: Optimized touch controls
- Mobile: Stacked layout, thumbnail grid below

✅ **YouTube Integration**
- Full YouTube IFrame API integration
- Auto-pause when switching videos
- Direct "Watch on YouTube" links
- Proper embed controls

✅ **Tactical Aesthetics**
- Industrial black/red theme matching site
- Corner accent borders (tactical crosshairs)
- Ammo counter-style video index
- Grid overlay background
- Military serial number styling

✅ **Interactive Controls**
- Previous/Next arrow buttons
- Thumbnail navigation (click any video)
- Keyboard navigation (arrow keys)
- Hover states with smooth transitions

✅ **Performance**
- Lazy loading for thumbnails
- Efficient video switching (no reload)
- Smooth CSS transitions
- Minimal JavaScript overhead

## Customization Options

### Change Video Titles/Descriptions
Edit the `videos` array in the JavaScript section:
```javascript
const videos = [
    {
        id: 'rccDTxeJaRM',
        title: 'Your Custom Title Here',
        description: 'Your custom description',
        thumbnail: 'https://img.youtube.com/vi/rccDTxeJaRM/maxresdefault.jpg'
    },
    // ... more videos
];
```

### Add More Videos
Simply add more objects to the `videos` array:
```javascript
{
    id: 'NEW_VIDEO_ID',
    title: 'New Video Title',
    description: 'Description here',
    thumbnail: 'https://img.youtube.com/vi/NEW_VIDEO_ID/maxresdefault.jpg'
}
```

The carousel will automatically adjust the grid and counter.

### Modify Colors
All colors use Tailwind classes. Key color classes:
- `bg-red-600` - Primary red accent
- `border-red-600` - Red borders
- `text-red-500` - Red text
- `bg-zinc-900` - Dark backgrounds
- `border-zinc-800` - Dark borders

### Adjust Spacing
Change padding/margin on the main container:
- `py-20 md:py-28` - Vertical padding (top/bottom)
- `px-4 sm:px-6` - Horizontal padding (sides)

## Browser Compatibility

✅ Modern browsers (Chrome, Firefox, Safari, Edge)
✅ Mobile browsers (iOS Safari, Chrome Mobile)
✅ Requires JavaScript enabled
✅ YouTube IFrame API must be accessible

## Testing Checklist

After integration, verify:
- [ ] All 3 videos load correctly
- [ ] Navigation arrows work (prev/next)
- [ ] Thumbnail clicks switch videos
- [ ] Keyboard arrows work
- [ ] "Watch on YouTube" link opens correct video
- [ ] Mobile responsive (test on phone)
- [ ] Hover states work on thumbnails
- [ ] Video info overlay appears on hover

## Deployment

Once tested locally:

```bash
# From ~/Sites/GRIZZLY-WEB
rsync -avz --delete ./index.html theoracle:/var/www/grizzlyarmament.com/
```

Or via your existing deployment process.

## Support

The carousel uses:
- **Tailwind CSS** (already loaded via CDN in your site)
- **YouTube IFrame API** (loaded automatically by the component)
- **Vanilla JavaScript** (no additional dependencies)

All code is self-contained in the section you paste.
