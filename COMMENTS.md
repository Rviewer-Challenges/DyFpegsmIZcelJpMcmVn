# Challenge Comments

For the **Twitter mirroring** page the next technologies have been chosen:

## Technologies

### Svelte + Vite
[![Svelte](https://img.shields.io/badge/svelte-white?style=for-the-badge&logo=svelte)](https://svelte.dev/)
[![Vite](https://img.shields.io/badge/vite-yellow?style=for-the-badge&logo=vite)](https://vitejs.dev/)

Since the project aims to be only a visual replication of an existing page and the workload in the browser will be minimal, the use of another JS framework would be an overkill, **Svelte** does the most of the work in the build phase, so it looked ideal for the task providing updates to the DOM only when the state of the app changes. 

**Vite** was choosen as its build tool since it provides a great developer experience and its compability with **Svelte**, even though **SvelteKit** being the official application framework, It is still in *beta* as of now.
 

### Tailwind CSS
[![Tailwind](https://img.shields.io/badge/tailwind%20css-0f172a?style=for-the-badge&logo=tailwindcss)](https://tailwindcss.com/)

There will be a lot of CSS to ~~steal~~ replicate in the project and a limited time to do so, for that reason a CSS framework for styling pages rapidly was needed. Hence **Tailwind CSS** was my choice for that purpose.

### Google Icon fonts + Images
[![Material Symbols](https://img.shields.io/badge/google%20fonts-white?style=for-the-badge&logo=googlefonts)](https://fonts.google.com/icons)

For images, I chose the **Material Symbols** so that it is easy to search and load from its extensive icon library. For very custom icons, images from web libraries online will be used directly instead.


## Development process

### Setup
First part will be setting up all what is needed for the project, doing the planning, chose the technologies to use and do a rough folder structure so that adding new pieces of the page are easy.

### Build
Here I plan to spend most of my time building views and components to display the data in the required way for the challenge, also defining the mocks to be used so that they are easily loaded in the views.

### Refine
Here I will make sure that nothing is missing in the pages and components built. 

### Deliver
Getting a server to deploy the project and raise the pull request to complete the challenge (No hosting has been chosen yet).

[Go Back](./README.md).
