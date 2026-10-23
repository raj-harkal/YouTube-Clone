# 🎬 YouTube Clone — Modern Video Streaming Web Application

![React 18](https://img.shields.io/badge/React-18.x-61DAFB?style=flat-square&logo=react&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3.x-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![HTML5 Video](https://img.shields.io/badge/HTML5-Video_Streaming-E34F26?style=flat-square&logo=html5&logoColor=white)
![Persistence](https://img.shields.io/badge/State-LocalStorage_%26_Firebase-FFCA28?style=flat-square&logo=firebase&logoColor=black)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

A responsive, feature-rich **YouTube Web Application Clone** built with **React 18** and **Tailwind CSS**. Designed to replicate the core user experience and visual fidelity of modern video-sharing platforms, this project includes real-time search and filtering, an HTML5 video player with chapter seeking and Theater Mode, interactive comments, channel subscriptions, and persistent user state.

---

## ✨ Key Features

### 🏠 Homepage & Discovery Feed
- **Sticky Navigation Header:** Includes brand logo navigation, real-time search input with trending query suggestions, voice search simulator modal, Creator Studio upload trigger, unread notifications popover, and theme switcher.
- **Collapsible Navigation Sidebar:**
  - **Desktop:** Toggles smoothly between a full navigation drawer and a compact mini-rail.
  - **Mobile:** Responsive slide-over drawer with backdrop blur.
  - **Views:** *Home*, *Subscriptions*, *Library*, *History*, *Liked Videos*, and *Watch Later*.
- **Category Filter Chips:** Horizontal scrollable chip bar (*All, Coding, AI & Tech, Gaming, Music, Live, News, Science, Design*) for instant feed filtering.
- **Dynamic SVG Thumbnail Engine:** Custom procedural SVG thumbnail artwork with hover progress bars, duration badges, and animated `LIVE` indicators.

### 📺 Video Watch Page
- **HTML5 Video Player:**
  - Streams open-source HD MP4 videos (Blender Open Movie Project / Google Cloud sample streams).
  - **Playback Speed Controls:** Cycle through `0.75x`, `1x`, `1.25x`, `1.5x`, and `2x` speeds.
  - **Theater Mode:** Expand the video player across the viewport width on desktop screens.
  - **Autoplay Next:** Optional toggle to automatically advance to the next recommended video when playback finishes.
  - **Stream Error Recovery:** Built-in fallback UI with one-click stream retry if network connectivity drops.
- **Interactive Video Metadata:**
  - **Subscribe / Subscribed Toggle:** Real-time subscriber count updates and toast notifications.
  - **Segmented Like / Dislike Bar:** Optimistic UI updates persisted across sessions.
  - **Share Modal:** One-click clipboard link copying.
  - **Save to Watch Later:** Bookmark videos directly from the player or card action menus.
- **Smart Expandable Description:** Supports *"Show more / Show less"* toggling and parses `MM:SS` timestamps (e.g., `00:15`) into interactive buttons that seek the video player directly to that chapter.

### 💬 Community & Creator Studio
- **Interactive Comments Section:**
  - Post new comments in real time.
  - Sort comments by **Top comments** or **Newest first**.
  - Like comments, pre-fill `@replies`, and delete your own comments.
- **Creator Studio Video Upload Modal:**
  - Publish custom videos with a title, category, description/chapters, and video stream source that immediately appear in the feed.

### 🎨 Design & Persistence
- **Dark & Light Mode:** Native dark theme (`#0f0f0f`) inspired by YouTube's modern ambient UI, plus a clean high-contrast light mode.
- **Full State Persistence:**
  - `index.html` persists all user data (likes, dislikes, subscriptions, watch history, saved videos, custom uploads, comments, and theme preference) in **`localStorage`**.
  - `App.jsx` supports real-time cloud synchronization via **Firebase Authentication & Firestore** alongside local state.

---

## 📂 Project Structure

This project is provided in two formats so you can either run it immediately in any web browser with zero setup or integrate it into a modern React/Vite build pipeline:

```text
├── index.html   # Standalone, zero-build version (runs directly in Chrome via double-click)
├── App.jsx      # Modular React Single-File Component (for Vite / Next.js / CRA projects)
└── README.md    # Project documentation
```

---

## 🚀 Getting Started

### Option 1: Run Immediately in Google Chrome (Zero Setup)
Use the standalone **`index.html`** file if you want to run the app right away without installing Node.js or running terminal commands.

1. Download **`index.html`** to your computer.
2. Double-click **`index.html`** (or right-click $\rightarrow$ **Open with** $\rightarrow$ **Google Chrome**, Edge, Safari, or Firefox).
3. The application will load immediately using React 18, Tailwind CSS, and Babel Standalone via CDN, with all interactions saved to your browser's `localStorage`.

---

### Option 2: Run in a Local React / Vite Development Environment
If you want to customize and build the **`App.jsx`** file inside a local React project (e.g., inside VS Code):

#### 1. Scaffold a new Vite + React project
```bash
npm create vite@latest youtube-clone -- --template react
cd youtube-clone
```

#### 2. Install dependencies
```bash
npm install lucide-react firebase
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

#### 3. Replace `src/App.jsx`
Copy the contents of **`App.jsx`** into `src/App.jsx` and start the development server:

```bash
npm run dev
```

Open `http://localhost:5173` in your browser to view the app.

---

## 🧭 Usage Guide & Interactive Walkthrough

| Feature | How to Test It |
| :--- | :--- |
| **Real-Time Search** | Click the top search bar to view trending suggestions, or type keywords like `WebGPU`, `Gaming`, or `System Design` to filter the video grid instantaneously. |
| **Voice Search** | Click the **Microphone icon** next to the search bar and select a voice preset chip to test instant voice filtering. |
| **Chapter Seeking** | Open any video, click **...more** inside the description box, and click a blue timestamp badge (e.g., `00:15`) to jump the video player to that timestamp. |
| **Upload a Video** | Click the **+ Create** button in the top-right header, enter a title and category, and click **Publish Video** to watch your newly uploaded video immediately. |
| **Manage Watch Later** | Click the three-dot menu (`⋮`) on any video card or the **Save** button underneath the video player, then visit **Watch Later** in the left sidebar. |
| **Refresh Persistence** | Like a video, subscribe to a channel, or post a comment, then refresh your browser tab—your changes remain intact via `localStorage`. |

---

## 🛠️ Tech Stack

- **UI Framework:** React 18 (`useState`, `useEffect`, `useMemo`, `useRef`)
- **Styling:** Tailwind CSS (Responsive CSS Grid, Flexbox, Dark/Light theming, custom scrollbars)
- **Icons:** Inline Lucide SVG Icons (zero external icon runtime overhead in `index.html`; `lucide-react` in `App.jsx`)
- **Media Playback:** Native HTML5 `<video>` API (custom playback rate, chapter seeking, autoplay chaining, error handling)
- **Storage & State:** Browser `localStorage` API (`index.html`) / Firebase Firestore (`App.jsx`)

---

## 📄 License

This project is open-source and available under the **MIT License** for educational and portfolio use.