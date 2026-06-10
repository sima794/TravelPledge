# Vercel Speed Insights Integration Guide

This guide shows how to integrate Vercel Speed Insights into the TravelPledge application.

## Package Installation

The `@vercel/speed-insights` package has been added to `package.json`. Run the following command to install:

```bash
pnpm install
```

## Integration Steps

### For React + Vite Projects

According to the official Vercel documentation, add the SpeedInsights component to your main application file.

#### Step 1: Import the Component

In your main app file (typically `src/App.tsx` or `src/main.tsx`), import the SpeedInsights component:

```typescript
import { SpeedInsights } from '@vercel/speed-insights/react';
```

#### Step 2: Add the Component to Your App

Add the `<SpeedInsights />` component to your main application component:

**Option A: In App.tsx (Recommended)**

```typescript
import { SpeedInsights } from '@vercel/speed-insights/react';

export default function App() {
  return (
    <>
      {/* Your existing app content */}
      <SpeedInsights />
    </>
  );
}
```

**Option B: In main.tsx**

```typescript
import React from 'react';
import ReactDOM from 'react-dom/client';
import { SpeedInsights } from '@vercel/speed-insights/react';
import App from './App';
import './index.css';

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <App />
    <SpeedInsights />
  </React.StrictMode>
);
```

## Example Implementation

Here's a complete example of how to integrate Speed Insights into a typical Vite + React app:

### src/App.tsx

```typescript
import { SpeedInsights } from '@vercel/speed-insights/react';

function App() {
  return (
    <div className="App">
      {/* Your application components */}
      <SpeedInsights />
    </div>
  );
}

export default App;
```

## Verification

After deployment to Vercel:

1. Navigate to your Vercel dashboard
2. Select your project
3. Go to the "Speed Insights" tab
4. Enable Speed Insights for your project
5. Deploy your application
6. Visit your live site to start collecting performance data

## Mobile (Capacitor) Considerations

Since this project uses Capacitor for mobile deployment, the Speed Insights integration will work automatically in the web version. For native mobile apps, performance tracking will occur when the app loads web content.

## Additional Resources

- [Vercel Speed Insights Quickstart](https://vercel.com/docs/speed-insights/quickstart)
- [Speed Insights Documentation](https://vercel.com/docs/speed-insights)
