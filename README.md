Requirements
Node.js: Version >= 18
Docker: Installed and running
Docker Compose: Installed and configured
GitHub Repository: For version control

For Hot Reload:
my-nextjs-project/
├── Dockerfile
├── docker-compose.yml
├── package.json
├── pnpm-lock.yaml (or yarn.lock)
├── public/
├── src/
│   ├── app/
│   ├── pages/
│   ├── components/
│   └── styles/
└── next.config.ts


update configuration as below:
import { Configuration } from 'webpack';

const nextConfig = {
  webpackDevMiddleware: (config: Configuration) => {
    config.watchOptions = {
      poll: 1000, // Check for changes every second
      aggregateTimeout: 300, // Delay before rebuilding
    };
    return config;
  },
};

export default nextConfig;



