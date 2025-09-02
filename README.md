
// app/layout.tsx import "./globals.css"; import { Inter } from "next/font/google";

const inter = Inter({ subsets: ["latin"] });

export const metadata = { title: "Digital Traffic Hub", description: "Produits digitaux et reels marketing", };

export default function RootLayout({ children }: { children: React.ReactNode }) { return ( <html lang="fr"> <body className={inter.className + " bg-black text-white"}>{children}</body> </html> ); }

// app/page.tsx import Link from "next/link";

export default function Home() { return ( <main className="flex flex-col items-center justify-center min-h-screen text-center p-8"> <h1 className="text-4xl font-bold text-red-600 mb-4"> 🚀 Bienvenue sur Digital Traffic Hub </h1> <p className="text-lg text-gray-300 max-w-2xl mb-6"> Découvrez nos produits digitaux et nos stratégies de trafic avec des reels inspirés de YouTube. </p> <div className="flex gap-4"> <Link
href="/produits"
className="bg-red-600 px-6 py-3 rounded-xl text-white font-semibold hover:bg-red-700"
> Voir Produits </Link> <Link
href="/blog"
className="bg-white text-black px-6 py-3 rounded-xl font-semibold hover:bg-gray-200"
> Lire Blog </Link> </div>

{/* Exemple d'intégration Reels (YouTube embed) */}
  <div className="mt-10 w-full max-w-xl">
    <iframe
      className="w-full aspect-video rounded-xl shadow-lg"
      src="https://www.youtube.com/embed/dQw4w9WgXcQ"
      title="YouTube video"
      allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
      allowFullScreen
    ></iframe>
  </div>
</main>

); }

// app/produits/page.tsx export default function Produits() { const products = [ { id: 1, name: "Ebook CPA Secrets", desc: "Apprends les bases du trafic CPA.", link: "#" }, { id: 2, name: "Formation Arbitrage", desc: "Domine l’arbitrage Facebook & TikTok.", link: "#" }, { id: 3, name: "Pack Templates Funnels", desc: "Funnels prêts à l’emploi.", link: "#" }, ];

return ( <main className="p-8 text-center"> <h1 className="text-3xl font-bold text-red-600 mb-6">Nos Produits Digitaux</h1> <div className="grid md:grid-cols-3 gap-6"> {products.map((p) => ( <div
key={p.id}
className="bg-gray-900 p-6 rounded-2xl shadow-lg border border-red-600"
> <h2 className="text-xl font-semibold mb-2">{p.name}</h2> <p className="text-gray-400 mb-4">{p.desc}</p> <a
href={p.link}
className="bg-red-600 px-4 py-2 rounded-lg text-white font-medium hover:bg-red-700"
> Acheter </a> </div> ))} </div> </main> ); }

// app/blog/page.tsx export default function Blog() { return ( <main className="p-8 max-w-3xl mx-auto"> <h1 className="text-3xl font-bold text-red-600 mb-6">Articles Marketing</h1> <article className="mb-6"> <h2 className="text-xl font-semibold mb-2">Comment générer du trafic CPA ?</h2> <p className="text-gray-300"> Le trafic CPA est basé sur la conversion. Pour réussir, il faut... </p> </article> <article> <h2 className="text-xl font-semibold mb-2">Arbitrage Facebook Ads</h2> <p className="text-gray-300">L’arbitrage publicitaire consiste à...</p> </article> </main> ); }

// app/contact/page.tsx export default function Contact() { return ( <main className="p-8 text-center"> <h1 className="text-3xl font-bold text-red-600 mb-6">Contact</h1>

