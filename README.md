# Happy-Birthday-
Happy Birthday 
import { useRef, useState } from "react";
import { motion } from "framer-motion";

export default function BirthdayWebsite() {
  const [opened, setOpened] = useState(false);
  const [photo1, setPhoto1] = useState(null);
  const [photo2, setPhoto2] = useState(null);
  const [photo3, setPhoto3] = useState(null);
  const [photo4, setPhoto4] = useState(null);

  const inputRef1 = useRef(null);
  const inputRef2 = useRef(null);
  const inputRef3 = useRef(null);
  const inputRef4 = useRef(null);

  const handleImageUpload = (e, setPhoto) => {
    const file = e.target.files[0];
    if (file) {
      const imageUrl = URL.createObjectURL(file);
      setPhoto(imageUrl);
    }
  };

  return (
    <div className="w-full min-h-screen overflow-hidden bg-[#F9A7B0] flex items-center justify-center relative">

      {/* ENVELOPE SCREEN */}
      {!opened && (
        <motion.div
          initial={{ opacity: 1 }}
          animate={{ opacity: opened ? 0 : 1 }}
          className="relative w-[350px] h-[350px] flex items-center justify-center"
        >
          {/* TOP ENVELOPE */}
          <div className="absolute rotate-[-20deg] w-[260px] h-[180px] bg-[#FDE4D0] border-2 border-[#5c4033] rounded-md">
            <div className="absolute top-0 left-0 w-full h-full">
              <div className="absolute top-0 left-0 w-1/2 h-full border-r border-[#5c4033] rotate-[35deg] origin-top-right"></div>
              <div className="absolute top-0 right-0 w-1/2 h-full border-l border-[#5c4033] rotate-[-35deg] origin-top-left"></div>
            </div>
          </div>

          {/* BOTTOM ENVELOPE */}
          <div className="absolute rotate-[10deg] w-[260px] h-[180px] bg-[#FDE4D0] border-2 border-[#5c4033] rounded-md"></div>

          {/* HEART BUTTON */}
          <motion.button
            whileTap={{ scale: 0.8 }}
            animate={{ scale: [1, 1.1, 1] }}
            transition={{ repeat: Infinity, duration: 1.5 }}
            onClick={() => setOpened(true)}
            className="absolute z-50 text-5xl"
          >
            ❤️
          </motion.button>
        </motion.div>
      )}

      {/* SCRAPBOOK PAGE */}
      {opened && (
        <motion.div
          initial={{ y: 100, opacity: 0, scale: 0.8 }}
          animate={{ y: 0, opacity: 1, scale: 1 }}
          transition={{ duration: 1, type: "spring" }}
          className="absolute inset-0 bg-[#F2EEE5] overflow-y-auto p-6 flex flex-col items-center"
        >
          {/* TITLE */}
          <h1 className="text-3xl text-center mt-6 text-[#1A2B56] font-light italic drop-shadow-sm">
            happy birthday mummum 😭🤍
          </h1>

          {/* LOVE STRIP */}
          <div className="absolute left-2 top-10 rotate-[-90deg] text-[#c59b6d] tracking-[10px] text-xl opacity-70">
            LOVE LOVE LOVE
          </div>

          {/* HEARTS */}
          <div className="absolute top-20 left-8 text-red-400 text-xl">♥</div>
          <div className="absolute top-40 right-10 text-red-400 text-2xl">♥</div>
          <div className="absolute bottom-40 left-12 text-red-300 text-xl">♥</div>

          {/* POLAROID SECTION */}
          <div className="mt-16 flex gap-6 flex-wrap justify-center">

            {/* PHOTO FRAME 1 */}
            <motion.div
              initial={{ y: -100, opacity: 0, scale: 1.2 }}
              animate={{ y: 0, opacity: 1, scale: 1 }}
              transition={{ type: "spring", stiffness: 100 }}
              onClick={() => inputRef1.current.click()}
              className="w-[170px] h-[240px] bg-white p-3 shadow-2xl rotate-[-8deg] cursor-pointer relative"
            >
              <div className="absolute top-2 left-5 w-16 h-5 bg-white/60 rotate-[-10deg]"></div>

              {photo1 ? (
                <img
                  src={photo1}
                  alt="Memory"
                  className="w-full h-[180px] object-cover"
                />
              ) : (
                <div className="w-full h-[180px] bg-[#222] flex items-center justify-center text-white text-sm text-center p-2">
                  Click To Add Your Photo 💖
                </div>
              )}

              <p className="text-center mt-3 text-[#1A2B56] text-sm">
                our favorite memory ✨
              </p>

              <input
                type="file"
                accept="image/*"
                ref={inputRef1}
                className="hidden"
                onChange={(e) => handleImageUpload(e, setPhoto1)}
              />
            </motion.div>

            {/* PHOTO FRAME 2 */}
            <motion.div
              initial={{ x: 100, opacity: 0, scale: 1.2 }}
              animate={{ x: 0, opacity: 1, scale: 1 }}
              transition={{ delay: 0.3, type: "spring" }}
              onClick={() => inputRef2.current.click()}
              className="w-[170px] h-[240px] bg-white p-3 shadow-2xl rotate-[6deg] cursor-pointer relative"
            >
              <div className="absolute top-2 left-5 w-16 h-5 bg-white/60 rotate-[8deg]"></div>

              {photo2 ? (
                <img
                  src={photo2}
                  alt="Memory"
                  className="w-full h-[180px] object-cover"
                />
              ) : (
                <div className="w-full h-[180px] bg-[#222] flex items-center justify-center text-white text-sm text-center p-2">
                  Upload Couple Photo 🤍
                </div>
              )}

              <p className="text-center mt-3 text-[#1A2B56] text-sm">
                forever with you 🌷
              </p>

              <input
                type="file"
                accept="image/*"
                ref={inputRef2}
                className="hidden"
                onChange={(e) => handleImageUpload(e, setPhoto2)}
              />
            </motion.div>
          </div>

          {/* PHOTO FRAME 3 */}
            <motion.div
              initial={{ y: 100, opacity: 0, scale: 1.2 }}
              animate={{ y: 0, opacity: 1, scale: 1 }}
              transition={{ delay: 0.5, type: "spring" }}
              onClick={() => inputRef3.current.click()}
              className="w-[170px] h-[240px] bg-white p-3 shadow-2xl rotate-[-4deg] cursor-pointer relative"
            >
              <div className="absolute top-2 left-5 w-16 h-5 bg-white/60 rotate-[5deg]"></div>

              {photo3 ? (
                <img
                  src={photo3}
                  alt="Memory"
                  className="w-full h-[180px] object-cover"
                />
              ) : (
                <div className="w-full h-[180px] bg-[#222] flex items-center justify-center text-white text-sm text-center p-2">
                  Add Another Memory 💕
                </div>
              )}

              <p className="text-center mt-3 text-[#1A2B56] text-sm">
                my safe place 🤍
              </p>

              <input
                type="file"
                accept="image/*"
                ref={inputRef3}
                className="hidden"
                onChange={(e) => handleImageUpload(e, setPhoto3)}
              />
            </motion.div>

            {/* PHOTO FRAME 4 */}
            <motion.div
              initial={{ x: -100, opacity: 0, scale: 1.2 }}
              animate={{ x: 0, opacity: 1, scale: 1 }}
              transition={{ delay: 0.7, type: "spring" }}
              onClick={() => inputRef4.current.click()}
              className="w-[170px] h-[240px] bg-white p-3 shadow-2xl rotate-[8deg] cursor-pointer relative"
            >
              <div className="absolute top-2 left-5 w-16 h-5 bg-white/60 rotate-[-6deg]"></div>

              {photo4 ? (
                <img
                  src={photo4}
                  alt="Memory"
                  className="w-full h-[180px] object-cover"
                />
              ) : (
                <div className="w-full h-[180px] bg-[#222] flex items-center justify-center text-white text-sm text-center p-2">
                  Upload Your Cute Photo 🌷
                </div>
              )}

              <p className="text-center mt-3 text-[#1A2B56] text-sm">
                together forever ✨
              </p>

              <input
                type="file"
                accept="image/*"
                ref={inputRef4}
                className="hidden"
                onChange={(e) => handleImageUpload(e, setPhoto4)}
              />
            </motion.div>
          </div>

          {/* BALLOONS */}
          <div className="absolute top-32 right-4 text-4xl flex flex-col gap-2">
            🎈🎈🎈
          </div>

          {/* LETTER */}
          <div className="mt-16 bg-[#f6e5cf] p-5 rounded-xl shadow-xl rotate-[-2deg] max-w-[320px] text-center">
            <h2 className="text-2xl mb-2">❤️</h2>
            <p className="text-[#5c4033] leading-7">
              P.S. I love you forever and ever 🤍
            </p>
          </div>

          {/* FLOWERS */}
          <div className="mt-10 text-5xl mb-20">
            🌷🌷🌷
          </div>
        </motion.div>
      )}
    </div>
  );
}
