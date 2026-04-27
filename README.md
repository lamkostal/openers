# Video Openers Project

This project is built using [Sapper](https://github.com/sveltejs/sapper), a framework for building high-performance web applications with Svelte. It provides a collection of video openers and templates that can be customized and exported for various use cases.

## Features

- **Dynamic Video Templates**: Easily customizable video openers for different purposes.
- **Svelte Components**: Modular and reusable components for building the UI.
- **Responsive Design**: Ensures compatibility across devices.
- **Static and Dynamic Routes**: Includes pages like About, Privacy, and Success.
- **MP4 Export Support**: Export video templates in MP4 format.

## Project Structure

- `src/`: Contains the source code, including components and routes.
  - `components/`: Reusable Svelte components like `Footer`, `Nav`, and `Modal`.
  - `routes/`: Pages of the application, such as `index.svelte` and `about.svelte`.
- `static/`: Static assets like global styles and manifest files.
- `__sapper__/`: Build output directory.
- `cypress/`: End-to-end testing setup with Cypress.

## Getting Started

### Prerequisites

Ensure you have Node.js installed on your system. You can download it from [nodejs.org](https://nodejs.org).

### Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd videopeners
   ```
2. Install dependencies:
   ```bash
   npm install
   ```

### Development

Run the project in development mode:
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to view the application.

### Building for Production

To build the project for production:
```bash
npm run build
```

The production-ready files will be in the `__sapper__/export` directory.

### Testing

End-to-end tests are set up using Cypress. To run the tests:
```bash
npm run test
```

## Learn More

- [Sapper Documentation](https://sapper.svelte.dev)
- [Svelte Documentation](https://svelte.dev)

## License

This project is licensed under the MIT License.
