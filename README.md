# anjaii-memew
import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Button } from "@/components/ui/button";
import { motion } from "framer-motion";

export default function BirthdayGreeting() {
  const [showMessage, setShowMessage] = useState(false);

  const funnyMessages = [
    "Met ultahh mewww.. anjayy yang lagi sweet seventeen nichh",
    "Hari ini spesial! like u bruhh(⁠ ⁠◜⁠‿⁠◝⁠ ⁠)⁠♡… ",
    "Semoga dengan seiring berjalannya waktu yang cepat ini, kmu kan selalu diberikan keberkahan ",
    "Tenang ajaa soal bertambahnya usia, kmu tetap terlihat awet muda karna senyummuu",
    "And the endd.. jgn pernah lupa bahwa.. 'innasholati wanusuki wamakhyaya wamamati lillahirabbil alamin' "
  ];

  const getRandomMessage = () => {
    return funnyMessages[Math.floor(Math.random() * funnyMessages.length)];
  };

  return (
    <div className="flex flex-col items-center justify-center h-screen bg-blue-100">
      <Card className="p-6 max-w-md text-center">
        <CardContent>
          <h1 className="text-2xl font-bold mb-4">🎉 Mett Menuaaa! 🎂</h1>
          {showMessage ? (
            <motion.p 
              className="text-lg mb-4" 
              initial={{ opacity: 0 }} 
              animate={{ opacity: 1 }}
            >
              {getRandomMessage()}
            </motion.p>
          ) : (
            <p className="text-lg mb-4">Klik tombol di bawah untuk mendapatkan ucapan ulang tahun yang lucu!</p>
          )}
          <Button onClick={() => setShowMessage(true)} className="bg-pink-500 text-white px-4 py-2 rounded-xl shadow-md">
            🎁 Buka Hadiah
          </Button>
        </CardContent>
      </Card>
    </div>
  );
}
