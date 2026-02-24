# CLAUDE.md — Game-Ruru

@AGENTS.md

## 專案資訊

- 網址：待定
- Repo：HelloRuru/Game-Ruru
- 部署：Cloudflare Pages（前端）+ Supabase（後端）

## 專案概述

宮鬥世代傳承文字遊戲。類《甄嬛傳》互動小說，玩家從甄選入宮開始，經歷後宮鬥爭，並透過世代傳承延續家族命運。

## 技術架構

- 前端：Next.js (App Router) + Tailwind CSS
- 後端/驗證：Supabase (Auth + PostgreSQL + Realtime)
- 部署：Cloudflare Pages

## 專案規則

- Mobile-first 響應式設計，手機體驗最重要
- 帳號密碼登入 + 雲端存檔
- 重要關頭自動存檔（進關卡前、重大決定前）
- 遊戲文字全部繁體中文
