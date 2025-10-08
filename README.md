# Ultra-Minimal Trading Game

A single-page React trading game with animated price movements and Solana Pay integration.

## Features

- **Animated Price Chart**: Green band moves up and down in a smooth sine wave
- **Tap-to-Bet**: Click on the right side of the screen inside the green band to place bets
- **Real-time Updates**: WebSocket connection for live price and player count updates
- **Solana Pay Integration**: QR codes for deposits and withdrawals
- **Mobile-First Design**: Optimized for mobile devices with touch interactions

## How to Play

1. **Launch Game**: Click "Launch Game" to start
2. **Set Stake**: Adjust your bet amount using the input field (0.5-12 USDC)
3. **Place Bets**: Tap anywhere on the right side of the screen (inside the green band)
4. **Watch Boxes**: Your bet boxes will slide to the right
5. **Win/Lose**: Boxes turn green if you win, red if you lose when they reach the finish line

## Tech Stack

- **Frontend**: React + Vite (single HTML file implementation)
- **Backend**: Express + WebSocket
- **Blockchain**: Solana (devnet)
- **Payment**: Solana Pay QR codes

## Installation

```bash
# Install backend dependencies
cd backend
npm install

# Install frontend dependencies  
cd ../frontend
npm install

# Start backend (port 4000)
cd ../backend
npm run dev

# Start frontend (port 3000)
cd ../frontend
npm run dev
```

## Game Mechanics

- **Price Movement**: White mid-line follows `y(t) = 200 + 80·sin(t/600)`
- **Green Band**: 30px tall, ±1% of current price
- **Bet Placement**: Only works on right half of screen (x ≥ 187px)
- **Box Animation**: Moves 2px per frame, 60fps
- **Win Condition**: Long position wins if price increases
- **Balance Updates**: Instant in-memory updates (no real money involved in demo)

## Solana Pay Integration

The game includes mock Solana Pay QR codes for:
- **Deposits**: Generate QR codes to receive USDC
- **Withdrawals**: Generate QR codes to send USDC

Note: This is a demo implementation using mock transactions. Real Solana integration would require actual wallet connections and transaction signing.

## Mobile Optimization

- Touch-friendly interface
- Optimized for 375×667 viewport
- 60fps animation on mobile devices
- No page refreshes or routing

## Development

The game follows the ultra-minimal specifications:
- Single HTML file frontend (≤180 lines)
- Single Express server file (≤150 lines)
- No external dependencies beyond React/Vite
- No database, no authentication
- Pure visual game experience