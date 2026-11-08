<p align="center">
  <img src="assets/banner.svg" alt="ABINFLIX - Cinema & Streaming Discovery Platform" width="100%" />
</p>

<p align="center">
  <strong>Cinematic Movie & TV Show Discovery Platform with TMDB API Integration, Official Trailers, and Infinite Exploration</strong>
</p>

<p align="center">
  <a href="https://abinflix.vercel.app/"><img src="https://img.shields.io/badge/Demo-abinflix.vercel.app-E50914.svg?style=for-the-badge&logo=vercel&logoColor=white" alt="Live Demo" /></a>
  <a href="https://github.com/AbinVarghexe/ABINFLIX/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge" alt="License" /></a>
  <a href="https://react.dev/"><img src="https://img.shields.io/badge/React-18.2-61DAFB.svg?style=for-the-badge&logo=react&logoColor=black" alt="React" /></a>
  <a href="https://vitejs.dev/"><img src="https://img.shields.io/badge/Vite-4.0-646CFF.svg?style=for-the-badge&logo=vite&logoColor=white" alt="Vite" /></a>
  <a href="https://redux-toolkit.js.org/"><img src="https://img.shields.io/badge/Redux%20Toolkit-1.9-764ABC.svg?style=for-the-badge&logo=redux&logoColor=white" alt="Redux" /></a>
  <a href="https://www.themoviedb.org/"><img src="https://img.shields.io/badge/API-TMDB%20v3-01D277.svg?style=for-the-badge" alt="TMDB" /></a>
</p>

---

## Highlights

- **Live Production App**: Deployed on Vercel at [abinflix.vercel.app](https://abinflix.vercel.app/).
- **Real-Time TMDB Integration**: Full catalog exploration powered by The Movie Database (TMDB) API across trending, top-rated, and upcoming movies & television series.
- **Embedded Trailer Playback**: Interactive modal video player (`react-player`) streaming official YouTube trailers and teasers.
- **Dynamic Filtering & Discovery**: Multi-parameter search by genre, sort order, and release year with lazy-loaded image optimization.
- **Smooth Infinite Scrolling**: High-performance paginated content rendering using `react-infinite-scroll-component`.
- **Global State Management**: Normalized movie configuration and genres cached in Redux Toolkit store to eliminate redundant network roundtrips.

## Architecture

```
                       +-----------------------------+
                       |    TMDB REST API (v3)       |
                       +--------------+--------------+
                                      | Axios HTTP (Bearer Auth)
                                      v
                       +-----------------------------+
                       |    Redux Toolkit Store      |
                       | - Configuration & Image Base |
                       | - Cached Genre Index        |
                       +--------------+--------------+
                                      |
         +----------------------------+----------------------------+
         |                                                         |
         v                                                         v
+-------------------------------+                         +-------------------------------+
| Home / Exploration Views      |                         | Media Details & Cast View     |
| - Carousel Sliders (Trending) |                         | - Rating Circular Progress    |
| - Infinite Scroll Grid        |                         | - Modal YouTube Player        |
| - Filter by Genre & Sort      |                         | - Similar & Recommended Feeds |
+-------------------------------+                         +-------------------------------+
```

## Quick Start

### 1. Prerequisites

- Node.js 18.0 or later
- A free API Read Access Token from [The Movie Database (TMDB)](https://www.themoviedb.org/settings/api)

### 2. Installation & Setup

```bash
# Clone the repository
git clone https://github.com/AbinVarghexe/ABINFLIX.git
cd ABINFLIX/frontend

# Install dependencies
npm install

# Configure environment variables
cp .env.example .env
```

Add your TMDB token to `frontend/.env`:

```env
VITE_APP_TMDB_TOKEN="your_tmdb_read_access_token_here"
```

### 3. Development Server

```bash
npm run dev
```

Visit `http://localhost:5173` to browse movies and TV series.

### 4. Production Build

```bash
npm run build
npm run preview
```

## Project Directory Layout

```
ABINFLIX/
├── assets/
│   └── banner.svg               # Vector visual banner
└── frontend/
    ├── public/                  # Favicons and static assets
    ├── src/
    │   ├── assets/              # Icons and fallback posters
    │   ├── components/          # Reusable UI widgets (Header, Footer, Carousel, VideoPopup)
    │   ├── hooks/               # Custom data-fetching hooks (useFetch)
    │   ├── pages/               # Route components (Home, Details, Explore, SearchResult, 404)
    │   ├── store/               # Redux slices and store configuration
    │   ├── utils/               # Axios TMDB API helper client
    │   ├── App.jsx              # Main routing tree
    │   └── main.jsx             # React DOM root entry
    ├── package.json
    └── vite.config.js
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
