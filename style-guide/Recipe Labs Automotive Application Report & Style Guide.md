**Recipe Labs Automotive: Application Report & Style Guide**  
**Part 1: Comprehensive Application Report**  
**1. Executive Summary**  
Recipe Labs Automotive is a sophisticated, AI-powered intelligence suite designed specifically for the modern car dealership. It serves as a centralized platform for dealership personnel—from salespeople to general managers—to leverage generative AI for enhancing sales, optimizing inventory, executing marketing campaigns, and analyzing performance.  
The application's core value proposition is augmenting the user's expertise by providing tailored, context-aware AI tools. It achieves this through a highly personalized experience, where the AI's "recipe" is trained on the dealership's specific market, brand focus, and goals. The user experience is designed to be futuristic, intuitive, and action-oriented, encouraging exploration and integration into daily workflows.  
**2. Application Architecture & Technology Stack**  
**2. Application Architecture & Technology Stack**  
The application is a modern, single-page application (SPA) built with a focus on performance, responsiveness, and a rich user experience.  
* **Frontend Framework:** **React 19** with **TypeScript** ensures a robust, type-safe, and component-based architecture.  
* **Styling:** **Tailwind CSS** is used for rapid, utility-first styling. The configuration is extended with a custom design system (colors, fonts, animations) to create a unique brand identity.  
* **AI Integration:** The **Google Gemini API** (@google/genai) is the exclusive backend for all generative AI tasks. The application intelligently crafts system instructions and user prompts based on the selected tool and the user's profile to elicit highly relevant responses.  
* **State Management:** The application primarily uses React's built-in hooks (useState, useEffect, useMemo) for local and component-level state. Global state (like the user profile) is managed at the top-level App.tsx component and passed down via props.  
* **Data Persistence:** User profiles, tool usage statistics, chat histories, and created automations are persisted in the browser's **localStorage**, enabling a consistent experience across sessions.  
* **External Integrations:** **Google Drive API** is integrated for saving generated reports, requiring Google Sign-In and OAuth2 for authorization.  
* **Progressive Web App (PWA):** A **Service Worker** (sw.js) provides offline functionality by caching the app shell and assets. The **Web App Manifest** (manifest.json) allows the app to be installed on a user's home screen for a native-like experience.  
**3. Core Features & User Flow**  
The user journey is designed to be seamless, from initial setup to daily use.  
1. **Onboarding & Personalization:**  
    * **Landing Page:** A visually striking, animated entry point establishes the futuristic brand identity.  
    * **Intake Modal:** A guided, multi-step process collects essential user and dealership information. This is a critical step, as this data forms the "Dealership Recipe" used to personalize all subsequent AI interactions.  
    * **Interactive Guide:** For first-time users, a non-intrusive onboarding guide uses a spotlight effect to highlight key dashboard features, ensuring a shallow learning curve.  
2. **The Dashboard (The Garage):**  
    * **Central Hub:** This is the main navigation screen, providing access to all features.  
    * **Smart Action Search:** A powerful search bar allows users to either find tools by name or type a natural language command (e.g., "write a Facebook ad for a Ford F-150"). The system intelligently maps this command to the most relevant tool and pre-fills the prompt.  
    * **AI Tools:** The core of the application is its extensive library of over 30 specialized tools, categorized into Sales, Inventory, Marketing, Finance, and Analytics. Users can toggle between a visual **Grid View** and a more compact **List View**.  
    * **Favorites:** Users can pin frequently used tools to a dedicated section at the top of the dashboard for quick access.  
    * **Recipes:** These are pre-defined, multi-step workflows that chain several AI tools together to solve complex problems (e.g., "Used Car Acquisition"). This feature guides users through best-practice processes.  
    * **Automations:** This advanced feature allows users to build, save, and run their own custom multi-step workflows using a dedicated **Automation Builder**. This empowers users to codify their unique processes.  
    * **AI Insights:** A dedicated modal synthesizes all user activity (tool usage, conversation history, automations) into a high-level strategic report, offering performance analysis and actionable recommendations.  
3. **Tool Interaction:**  
    * **Conversational UI:** Most tools are presented in a chat-like interface, making the interaction feel natural and intuitive.  
    * **Contextual Awareness:** The AI's system instructions are dynamically built using the user's profile, recent activity in other tools, and the specific tool's purpose, leading to highly relevant and personalized outputs.  
    * **Multimedia & Voice:** The UI supports file uploads (for image-based tools) and speech-to-text via the browser's Speech Recognition API, offering multiple input modalities.  
    * **Actionable Outputs:** AI responses are rendered as formatted Markdown and are accompanied by tools to **Copy**, **Download as .txt**, or **Save to Google Drive**. A satisfaction feedback mechanism (thumbs up/down) helps track model performance.  
**4. UI/UX Design Philosophy**  
* **Futuristic & Premium:** The dark-themed UI, subtle animations (glowing orbs, particle effects, hex grids), and use of the "Orbitron" display font create a sophisticated, high-tech "command center" feel.  
* **Clarity & Efficiency:** Despite the complex feature set, the information architecture is clear. Categories, search, and smart actions ensure users can find what they need with minimal friction.  
* **Responsive & Accessible:** The design is fully responsive, with a mobile-first approach that adapts layouts for smaller screens. The bottom-anchored category filter on mobile is a key example of touch-friendly design. ARIA attributes and keyboard navigation are considered.  
* **Engaging & Dynamic:** Micro-interactions, haptic feedback on mobile, and purposeful animations provide constant feedback, making the app feel alive and responsive. The "Level Up" modal hints at gamification elements that could be expanded to further drive engagement.  
  
**Part 2: Comprehensive Style Guide**  
**Part 2: Comprehensive Style Guide**  
This guide outlines the visual and interactive language of the Recipe Labs Automotive application.  
**1. Color Palette**  
The palette is built on a foundation of deep, dark tones accented by a vibrant, electric blue.  
* **Primary Brand Colors:**  
    * brand-deep-blue (#0D1B2A): Primary background and dark UI elements.  
    * brand-steel-gray (#415A77): Secondary UI elements, accents, and gradient component.  
    * brand-electric-blue (#00BFFF): The primary accent color for interactive elements, focus states, and highlights.  
    * brand-silver (#E0E1DD): Light text and UI elements.  
    * brand-racing-red (#D90429): Used for alerts, errors, and as a contrasting accent.  
* **Accent Color System:** The UI uses a CSS variable var(--accent-color) which is dynamically set based on user preference in settings, allowing for theming.  
* **Gradients:** Used for tool icons and cards to add visual depth.  
    * from-brand-deep-blue to to-brand-steel-gray  
    * from-brand-steel-gray to to-brand-electric-blue  
    * from-brand-electric-blue to to-brand-silver  
    * from-brand-racing-red to to-brand-steel-gray  
**2. Typography**  
A three-font system creates a clear visual hierarchy.  
* **UI & Body Text:** **Inter** (sans-serif). Chosen for its excellent readability at all sizes.  
    * Weights: Regular (400), Medium (500), Bold (700).  
* **Headings & Branding:** **Orbitron** (sans-serif, display). Gives the app its signature futuristic, high-tech feel. Used for major page titles and branding.  
* **Monospace & Data:** **Roboto Mono**. Used in input fields, code blocks, and for displaying data to convey precision and technicality.  
**3. Iconography**  
Icons are sourced from a consistent library (similar to Feather Icons) and adhere to a clean, outline style.  
* **Style:** Stroke-based, strokeWidth="2", rounded linecaps and joins.  
* **Size:** Standardized at 24x24 pixels for cards and 20x20 for smaller buttons.  
* **Usage:** Each icon is semantically chosen to represent its function (e.g., <Zap> for automations, <Layers> for recipes, <Handshake> for Sales category).  
**4. Layout & Spacing**  
A consistent spacing scale based on 0.25rem units (Tailwind's default) is used throughout.  
* **Page Padding:** p-4 sm:p-6 lg:p-8  
* **Card Padding:** p-4 sm:p-6  
* **Gaps:** gap-4 sm:gap-6 between grid items.  
* **Corner Radii:** Generous rounding is used to create a modern, soft aesthetic.  
    * Cards & Modals: rounded-2xl or rounded-3xl.  
    * Buttons & Inputs: rounded-lg.  
**5. Components**  
* **Cards (Tool/Recipe/Automation):**  
    * bg-white dark:bg-black/50, border border-gray-200 dark:border-white/10, rounded-2xl.  
    * Hover State: Elevates slightly (hover:-translate-y-1) and reveals a prominent shadow (hover:shadow-2xl hover:shadow-[rgba(var(--accent-color-rgb),0.2)]).  
* **Buttons:**  
    * **Primary Action:** Gradient background (from-brand-steel-gray to-brand-electric-blue), bold text, hover:scale-105 transform, and a gradient shadow.  
    * **Secondary:** Flat background (bg-gray-100 dark:bg-white/10), changes color on hover.  
    * **Filter/Category:** Pill-shaped (rounded-full), changes from flat to a solid accent color when active.  
* **Modals:**  
    * **Backdrop:** bg-black/80 backdrop-blur-md.  
    * **Container:** bg-white dark:bg-black, rounded-3xl, prominent accent shadow.  
    * **Animation:** Enters with animate-scaleIn and animate-fadeIn.  
* **Inputs:**  
    * font-mono, bg-white dark:bg-black/30, border-2, rounded-lg.  
    * **Focus State:** A 2px ring using var(--accent-color).  
**6. Visual Effects & Animations**  
Animations are used to provide feedback and enhance the futuristic aesthetic without being distracting.  
* **Background Effects (Dark Mode):** HexGridBackground, ParticleEffect, and FloatingOrb create a dynamic, deep space environment.  
* **Loading States:**  
    * AILoader: Three pulsing vertical bars for AI thinking states.  
    * Loader: A spinning line icon for saving/loading data.  
* **Entry Animations:**  
    * animate-fadeIn: For modals and new content.  
    * animate-scaleIn: For modals to pop into view.  
    * animate-slideInUp: For chat messages to appear sequentially.  
* **Hover/Active States:** Smooth transitions (transition-all duration-200) are applied to all interactive elements.  
