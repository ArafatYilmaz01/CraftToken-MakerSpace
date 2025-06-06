# 🎨 CraftToken MakerSpace Platform

A decentralized platform to tokenize traditional crafts and support master artisans. Built with Next.js and the Stellar blockchain, it allows artisans to preserve cultural heritage while receiving direct support from a global community.

---

## ✨ Features

- 🛍️ Traditional Craft Gallery  
- 🧓 Master Artisan Support  
- 🪙 Tokenized Ownership via Stellar Soroban  
- 🔐 Compliance & Whitelist Verification  
- 📜 Asset Metadata & Valuation  
- 🚀 Secure Transfers with Freighter Wallet  
- 📲 Fully Responsive UI (shadcn/ui + TailwindCSS)  

---

## ⚙️ Tech Stack

- **Frontend**: Next.js 14, TypeScript, Tailwind CSS, shadcn/ui  
- **Blockchain**: Stellar Soroban (Testnet)  
- **Wallet**: Freighter Wallet  
- **State Management**: Zustand  
- **Other**: Stellar SDK, Soroban Client, Custom Hooks  

---

## 🚀 Quick Start

### 📦 Prerequisites

- Node.js ≥ 18  
- Freighter Wallet browser extension  
- Access to Stellar Testnet  

### 📥 Installation

```bash
git clone https://github.com/yourusername/rwa-frontend.git
cd rwa-frontend
npm install
npm run dev
```

Open `http://localhost:3000` to view in browser.

### 🏗️ Build for Production

```bash
npm run build
npm start
```

---

## 🧾 Project Structure

```
rwa-frontend/
├── app/
│   ├── page.tsx             # Main dashboard
│   ├── transfer/page.tsx    # Transfer form
│   └── layout.tsx           # Root layout
├── components/
│   ├── ui/                  # shadcn/ui components
│   └── layout/              # Header, Container
├── lib/
│   ├── contract.ts          # Soroban smart contract methods
│   ├── types.ts             # Global types
│   ├── stellar.ts           # Stellar utilities
│   └── utils.ts             # Helper functions
├── stores/
│   ├── wallet.ts            # Zustand wallet state
│   └── contract.ts          # Zustand contract state
└── public/                  # Static assets
```

---

## 🔗 Smart Contract Details

### ✅ Supported Operations

- Get Asset Metadata  
- Check Compliance  
- Query User Token Balance  
- Perform Transfers  
- Verify Whitelist Status  

### 🧩 Contract Metadata

```ts
interface AssetMetadata {
  name: string;
  symbol: string;
  asset_type: string;
  valuation: string;
  last_valuation_date: number;
  legal_doc_hash: string; // simulated hash
}
```

### 🔒 Compliance Format

```ts
interface ComplianceData {
  kyc_verified: boolean;
  accredited_investor: boolean;
  jurisdiction: string;
  compliance_expiry: number;
}
```

---

## 💼 Dashboard Features

- 📊 Token Balance + Valuation  
- ✅ KYC / Whitelist Status  
- 🔄 Transfer Form (to Stellar address)  
- 🔍 Asset Details + Legal Metadata  
- ⚠️ Error Handling and Status Indicators  

---

## 🌐 Environment Variables

Create a `.env.local` file with the following:

```env
NEXT_PUBLIC_STELLAR_NETWORK=testnet
NEXT_PUBLIC_CONTRACT_ID=your_contract_id_here
```

---

## 🧠 Freighter Integration

```ts
import {
  isConnected,
  requestAccess,
  getNetworkDetails,
  getPublicKey
} from '@stellar/freighter-api';

const connect = async () => {
  const connected = await isConnected();
  if (!connected) await requestAccess();
  const address = await getPublicKey();
  return address;
};
```

---

## 🎨 UI/UX

- Tailored for artisans & investors  
- Earth-toned palette  
- Accessible fonts and color contrast  
- Minimal and craft-inspired layout  

---

## 📅 Roadmap

### 🔹 v1 - MVP (✅ Complete)

- Static metadata  
- Token balance + transfer  
- Testnet contract support  

### 🔹 v2 - In Progress

- Dynamic data from backend/smart contract  
- Asset marketplace  
- KYC simulation flow  

### 🔹 v3 - Planned

- Real valuation updates  
- Tokenization wizard  
- Admin dashboard  
- Mobile app (React Native or PWA)  

---

## 🧪 Testing

### Currently using:

- Manual testnet simulation  
- Mock contract client  
- Validation and edge cases  

### Planned:

- Unit testing with Jest  
- Integration tests with Playwright or Cypress  
- Contract simulation tests  

---

## 📋 License

This project is licensed under the MIT License. See `LICENSE.md` for more details.

---

## 🙌 Acknowledgements

- Stellar Developers  
- Freighter Wallet  
- shadcn/ui  
- Tailwind CSS  
- Next.js  
