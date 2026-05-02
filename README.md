# 🌙 Usman Hadi — Memory Page

> **Live:** [usman.ami.bd](http://usman.ami.bd)

একটি luxury Black & Gold থিমের ডিজিটাল স্মৃতির পাতা — উসমান হাদীর জন্য।

---

## 📁 সম্পূর্ণ ফাইল স্ট্রাকচার

```
usman-hadi/
├── index.html              ← মেইন পেজ (সব কিছু এখানে)
├── README.md               ← এই ফাইল
│
├── photos/
│   ├── manifest.json       ← গ্যালারির ছবির লিস্ট
│   ├── profile.jpg         ← প্রোফাইল ছবি (যেকোনো extension)
│   ├── photo-001.jpg       ← গ্যালারি ছবি
│   ├── photo-001.json      ← ছবির title & caption
│   ├── photo-002.jpg
│   ├── photo-002.json
│   └── ...
│
└── audio/
    └── bgm.mp3             ← ব্যাকগ্রাউন্ড মিউজিক
```

---

## 🎵 Audio যোগ করার নিয়ম

### Step 1 — ফোল্ডার বানাও
```
audio/
└── bgm.mp3
```

### Step 2 — Supported formats
| Format | Extension | Notes |
|--------|-----------|-------|
| MP3 | `bgm.mp3` | সব browser সাপোর্ট করে ✅ |
| OGG | `bgm.ogg` | Firefox এর জন্য ভালো |
| M4A | `bgm.m4a` | iOS Safari এর জন্য ভালো |
| WAV | `bgm.wav` | Uncompressed, বড় সাইজ |

> ফাইলের নাম অবশ্যই **`bgm`** হতে হবে।  
> Code নিজেই `bgm.mp3` → `bgm.ogg` → `bgm.m4a` → `bgm.wav` অর্ডারে খুঁজবে।

### Step 3 — Audio না থাকলে?
`audio/` ফোল্ডার বা ফাইল না থাকলে **Synthesized ambient music** অটো চালু হবে।  
Web Audio API দিয়ে তৈরি, কোনো ফাইল ছাড়াই।

### 🎶 ভালো BGM পাওয়ার জায়গা (Free)
- [pixabay.com/music](https://pixabay.com/music) → Search: `lullaby`, `islamic nasheeed`, `soft ambient`
- [freemusicarchive.org](https://freemusicarchive.org)
- [soundcloud.com](https://soundcloud.com) → Free download filter

### ⚠️ Audio Tips
- ফাইল সাইজ **5MB এর নিচে** রাখো (GitHub Pages limit)
- Loop করার দরকার নেই — code নিজেই loop করে
- মোবাইলে audio চালু করতে user কে **♪ বাটন** press করতে হবে  
  *(Browser policy — autoplay block করে)*

---

## 📸 Photos যোগ করার নিয়ম

### manifest.json আপডেট করো
```json
{
  "profile": "profile.jpg",
  "photos": [
    "photo-001.jpg",
    "photo-002.jpg",
    "photo-003.jpg"
  ]
}
```

### প্রতিটি ছবির জন্য .json বানাও
ফাইলের নাম হবে ছবির নামের মতোই, শুধু extension `.json`:

**`photo-001.json`**
```json
{
  "title": "First day",
  "titleBn": "প্রথম দিন",
  "caption": "Welcome to the world, little one ❤️",
  "captionBn": "পৃথিবীতে স্বাগতম, ছোট্ট সোনামণি ❤️"
}
```

### Supported image formats
`jpg` `jpeg` `png` `webp` `gif`

### Profile photo
`profile.jpg` রাখলে অটো detect করবে।  
`profile.png`, `profile.webp` ইত্যাদিও চলবে।

---

## 🚀 GitHub Pages Deploy

### Step 1 — Repository বানাও
```
GitHub → New Repository → Public → Create
```

### Step 2 — ফাইল upload করো
```
index.html
photos/
  manifest.json
  profile.jpg
  photo-001.jpg
  photo-001.json
  ...
audio/
  bgm.mp3
README.md
```

### Step 3 — Pages enable করো
```
Settings → Pages → Source: Deploy from branch
Branch: main → / (root) → Save
```

### Step 4 — Live!
```
https://yourusername.github.io/usman-hadi/
```

---

## 🌐 Custom Domain (usman.ami.bd)

### Step 1 — CNAME ফাইল বানাও
Repository তে `CNAME` নামে একটি ফাইল বানাও (extension নেই):
```
usman.ami.bd
```

### Step 2 — DNS Settings
Domain provider এ গিয়ে DNS record যোগ করো:

| Type | Name | Value |
|------|------|-------|
| CNAME | usman | yourusername.github.io |

অথবা Apex domain হলে:
| Type | Name | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

### Step 3 — GitHub Settings
```
Settings → Pages → Custom domain → usman.ami.bd → Save
✅ Enforce HTTPS চেক করো
```

---

## ✨ Features

| Feature | Details |
|---------|---------|
| 🌙 Theme | Black + Gold Luxury |
| 🎬 Intro | ১০ সেকেন্ড cinematic power-on |
| ❤️ Touch Effect | CSS hearts + sparkles + rings + stars |
| 🕐 Age Counter | Real-time seconds পর্যন্ত |
| 📅 Countdown | ১ম জন্মদিন পর্যন্ত live |
| 🌐 Language | EN / বাংলা toggle |
| 📸 Gallery | Polaroid style, lightbox, swipe |
| 🎵 Audio | File বা synthesized ambient |
| 🖱️ Cursor | Mouse-only trail (touch এ নেই) |
| 🔒 Security | Copy/right-click block |

---

## 📝 তথ্য আপডেট করতে

`index.html` এর একদম উপরে `CFG` object:

```js
const CFG = {
  name:    "Usman Hadi",
  nameBn:  "উসমান হাদী",
  nameAr:  "عُثْمَان هَادِي",
  birth:   "2026-04-12T18:30:00",   // জন্মের সঠিক সময়
  next:    "2027-04-12T18:30:00",   // পরের জন্মদিন
  ...
};
```

---

*Made with ❤️ for Usman Hadi — April 2026*
