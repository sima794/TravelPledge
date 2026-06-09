# TravelPledge 🧳

An **AI-powered multi-user trip planning platform** that helps groups organize collaborative vacations with real-time budget tracking and intelligent recommendations.

## 🎯 Hackathon Track
**Reasoning Agents** - Uses OpenAI's GPT-4o-mini to solve complex trip-planning problems through multi-step reasoning

## ✨ Key Features

### 🤖 AI Trip Advisor
- **Destination Suggestions**: AI analyzes group budget, preferences, and constraints to recommend affordable travel options
- **Budget Optimization**: Real-time wallet tracking and cost analysis across multiple travel groups
- **Multi-step Reasoning**: Agent breaks down decisions (budget → destination matching → itinerary building)
- **Rule Validation**: Enforces group travel rules and constraints during planning
- **Conversational Interface**: Chat-based interaction with typing indicators and smooth animations

### 👥 Group Management
- Create and manage multiple travel groups
- Real-time shared pool balance tracking
- Multi-user collaboration on trip planning
- Transaction history and payment tracking

### 📱 Cross-Platform Support
- **Web**: React + TypeScript + Tailwind CSS
- **iOS/Android**: Capacitor for native mobile deployment
- Responsive UI with Framer Motion animations

## 🏗️ Architecture

```
TravelPledge/
├── src/
│   ├── components/          # React components (Chat, Groups, etc.)
│   ├── lib/                # Utilities and helpers
│   ├── pages/              # Page components
│   └── main.tsx            # App entry point
├── index.html              # HTML entry
├── package.json            # Dependencies
├── tsconfig.json           # TypeScript config
├── vite.config.ts          # Vite web config
├── vite.config.mobile.ts   # Vite mobile config
├── capacitor.config.ts     # Capacitor mobile config
└── components.json         # shadcn/ui config
```

### Tech Stack
- **Frontend**: React 19, TypeScript, Tailwind CSS
- **UI Components**: shadcn/ui + Radix UI
- **Mobile**: Capacitor (iOS/Android)
- **AI**: OpenAI GPT-4o-mini API
- **Build**: Vite
- **Animations**: Framer Motion
- **Forms**: React Hook Form + Zod validation

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- npm or yarn
- Xcode (for iOS) / Android Studio (for Android)

### Web Development

```bash
# Install dependencies
npm install

# Start dev server
npm run dev
# Open http://localhost:5173

# Build for production
npm run build

# Preview production build
npm run serve

# Type checking
npm run typecheck
```

### Mobile Development

```bash
# Build and sync to iOS simulator
npm run cap:ios

# Build and sync to Android emulator
npm run cap:android

# Sync native projects (without building)
npm run cap:sync
```

## 🤖 AI Agent Capabilities

The TravelPledge AI Advisor uses OpenAI's API to provide intelligent trip planning:

1. **Destination Suggestion** ✈️
   - Analyzes group budget and preferences
   - Recommends affordable destinations with price comparisons
   - Considers group size and travel dates

2. **Budget Analysis** 💰
   - Tracks group pool balance across multiple groups
   - Calculates per-person costs
   - Suggests budget-friendly alternatives

3. **Itinerary Assistance** 📅
   - Helps structure multi-day trip plans
   - Suggests activities and attractions
   - Provides timing and logistics advice

4. **Rule Validation** ✅
   - Enforces group travel policies
   - Validates cost constraints
   - Ensures fairness in expense distribution

### Demo Mode
When no OpenAI API key is available, the app uses an intelligent fallback that:
- Pattern-matches user intents
- Generates contextually relevant responses using real data
- Simulates AI thinking with a 700-1300ms delay

## 🔐 Environment Setup

### For AI Features
Add your OpenAI API key:
```bash
# Create .env file
echo "VITE_OPENAI_API_KEY=your-api-key-here" > .env
```

### For Capacitor
```bash
# Set up iOS
cap add ios

# Set up Android
cap add android
```

## 📊 System Architecture

### Context System
The app maintains a fresh `AdvisorContext` snapshot on every message:
```typescript
interface AdvisorContext {
  currentUser: User | null;
  groups: Group[];
  transactions: Transaction[];
  users: User[];
}
```

This ensures the AI always has:
- Latest wallet balances
- Current group compositions
- Recent transaction history
- All available travel options

### Message Flow
1. User sends message → Immediately displays
2. Fresh context snapshot is read from localStorage
3. System prompt is built with user's real data
4. OpenAI (or demo mode) generates response
5. Response displays with typing indicator
6. Auto-scroll to latest message

## 🎨 UI/UX Features

- **Floating Action Button**: Smooth scale animations for chat access
- **Typing Indicator**: Animated bouncing dots while AI responds
- **Auto-scroll**: Smooth scroll to latest message
- **Responsive Design**: Works on mobile, tablet, desktop
- **Dark/Light Mode**: Theme support with next-themes
- **Accessible Components**: Built on Radix UI primitives

## 📝 Project Structure for Hackathon

```
✅ GitHub repository: https://github.com/sima794/TravelPledge
✅ Live demo: [Deployed on Vercel]
✅ Mobile-ready: iOS/Android builds via Capacitor
✅ AI-powered: GPT-4o-mini integration
✅ Production-ready: Vite build, TypeScript, testing
✅ Well-documented: README, inline code comments
```

## 🏆 Hackathon Submission

**Track**: Reasoning Agents
**Focus**: Multi-step AI reasoning for complex trip-planning scenarios
**Innovation**: Combines group finance management with intelligent conversational AI

## 📄 License

MIT

## 🤝 Contributing

Contributions welcome! Open an issue or pull request.

## 📞 Support

For questions about TravelPledge, open an issue on GitHub.

---

**Ready to plan your next group trip with AI? Deploy TravelPledge today!** 🚀
