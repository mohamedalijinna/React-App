# Full-Stack Application Starter

![Laravel Version](https://img.shields.io/badge/Laravel-11.x-FF2D20?style=flat-square&logo=laravel)
![React Version](https://img.shields.io/badge/React-18.x-61DAFB?style=flat-square&logo=react&logoColor=20232a)
![License](https://img.shields.io/badge/License-MIT-4c1d95?style=flat-square)

A modern full-stack web application starter kit utilizing **Laravel** for a robust, secure RESTful API backend and **React** for a responsive, component-driven user interface. This layout is preconfigured for efficient asset compilation and single-command workflows.

---

## 📂 Project Structure

This repository keeps a clean separation of concerns, managing back-end components alongside front-end elements compiled via Vite.

```text
├── app/                     # Laravel core application logic (Models, Controllers, Middleware)
├── bootstrap/               # Application bootstrapping and routing configuration setup
├── config/                  # Global application configuration profiles
├── database/                # Database migrations, structural seeders, and factories
├── public/                  # Exposed public web root directory
├── resources/
│   └── js/                  # React Application Source Root
│       ├── components/      # Reusable UI component blocks
│       ├── layouts/         # Shared structure wrappers (Navbar, Sidebar)
│       ├── pages/           # Routed view templates/screens
│       └── app.jsx          # React app mounter element
├── routes/                  # API and web routing engine configurations
├── .env.example             # Initial baseline environment configuration template
├── package.json             # Front-end packages, build targets, and dependencies
├── composer.json            # Back-end PHP framework packages and requirements
└── vite.config.js           # Asset bundling system configuration profiles