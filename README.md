# Devrehane – Electronics & Robotics E-Commerce Platform

Devrehane is an e-commerce project for electronics, robotics and maker components.

The project is built as a practical full-stack web application with a public storefront, admin panel, product/category management, order workflow, return workflow and transactional email notifications.

Live website: https://www.devrehane.net

## Tech Stack

- React
- Vite
- TypeScript
- Tailwind CSS
- Supabase Auth
- Supabase Database
- Supabase Row Level Security
- Supabase Storage
- Supabase Edge Functions
- Resend
- Vercel
- Git / GitHub

## Main Features

- Public e-commerce storefront
- Product and category management
- Admin panel with role-based access
- User authentication
- Separate admin and public authentication sessions
- Shopping cart and checkout-related structure
- Order status workflow
- Stock and inventory-related logic
- Return request workflow
- Transactional email notifications
- Password strength and authentication UX improvements
- Turkish user interface and SEO-friendly routing structure

## Security & Architecture Notes

- Supabase Row Level Security is used for access control.
- Admin functionality is separated from the public user flow.
- Authentication flows were designed with security and user experience in mind.
- Sensitive keys and production configuration are not stored in this public repository.
- The source code repository is private for security and business reasons.
- The project architecture focuses on maintainability, clear workflows and scalable feature development.

## Development Workflow

The project is developed with Git-based version control and tested locally before deployment.

AI-assisted development tools such as ChatGPT, Claude and Gemini are used for code analysis, debugging, documentation research and implementation support. Final integration, testing, architectural decisions and project validation are manually reviewed.

## Planned Extensions / Roadmap

- **IoT Interfaces:** Planned implementation of interfaces for real-time data visualization of sensor-based robotics prototypes.

- **AI-Assisted Subtractive Inventory System:** Planned development of a system where users can enter existing components or resources. The system would compare these resources with target project bills of materials (BOM), identify missing parts and generate optimized shopping lists or carts.

- **Project-Based Shopping Experience:** Users could select a target project, such as an Arduino robot, sensor prototype or electronics kit. The platform would calculate which components are already available to the user and which components still need to be purchased.

- **Cross-Domain Scalability:** The same logic could be adapted beyond electronics and robotics, for example to recipes, DIY projects or learning kits. The general concept is: target project requirements minus available user resources equals an optimized shopping list.

- **Sustainable Software Architecture:** The focus is on building an extendable architecture instead of a short-term prototype.

> These features are planned extensions and are not part of the current production version yet.

## Source Code

The main source code is kept in a private repository.

This public repository is used as a portfolio overview and case study for the Devrehane project.
