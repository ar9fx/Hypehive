<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes, viewport-fit=cover">
  <title>HYPEHIVE | Premium Digital Store</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
    }

    body {
      background: radial-gradient(circle at 10% 30%, #0a0c1a, #010103);
      color: #edf2ff;
      padding: 1.2rem 1rem 2.5rem;
      min-height: 100vh;
    }

    .container {
      max-width: 1350px;
      margin: 0 auto;
    }

    /* Glass header */
    .header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
      margin-bottom: 1.8rem;
      background: rgba(12, 20, 35, 0.65);
      backdrop-filter: blur(14px);
      border-radius: 2rem;
      padding: 1rem 1.8rem;
      border: 1px solid rgba(0, 230, 250, 0.4);
      box-shadow: 0 12px 25px -8px rgba(0,0,0,0.6);
    }
    .logo h1 {
      font-size: 2rem;
      background: linear-gradient(125deg, #b983ff, #2dd4bf);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.3px;
    }
    .logo p {
      font-size: 0.7rem;
      color: #8d9ee0;
    }
    .wallet-card {
      background: #0a1022cc;
      border-radius: 2rem;
      padding: 0.5rem 1.6rem;
      text-align: right;
      border-right: 3px solid #2dd4bf;
      border-left: 1px solid #3b4b7a;
    }
    .wallet-label {
      font-size: 0.7rem;
      letter-spacing: 1px;
      color: #a0b2fc;
    }
    .wallet-amount {
      font-size: 2rem;
      font-weight: 800;
      color: #e2b0ff;
      line-height: 1;
    }
    .ref-badge {
      font-size: 0.7rem;
      background: #1e2b3c;
      padding: 4px 12px;
      border-radius: 30px;
      margin-top: 6px;
      cursor: pointer;
    }

    /* deposit panel */
    .deposit-section {
      background: rgba(0, 0, 0, 0.5);
      backdrop-filter: blur(8px);
      border-radius: 1.8rem;
      padding: 1rem 1.5rem;
      margin-bottom: 2rem;
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
      border: 1px solid #2d3e66;
    }
    .btn-deposit {
      background: linear-gradient(95deg, #1f2e4a, #0e1a2c);
      border: 1px solid #3bc9db;
      color: white;
      font-weight: bold;
      padding: 0.7rem 1.8rem;
      border-radius: 3rem;
      cursor: pointer;
      transition: 0.2s;
    }
    .btn-deposit:hover {
      background: #2a3f62;
      box-shadow: 0 0 8px cyan;
    }

    /* section titles */
    .section-title {
      font-size: 1.6rem;
      margin: 1.8rem 0 1rem;
      border-left: 5px solid #c084fc;
      padding-left: 1rem;
      font-weight: 700;
    }
    .products-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
      gap: 1.3rem;
    }
    .product-card {
      background: rgba(10, 22, 40, 0.75);
      backdrop-filter: blur(4px);
      border-radius: 1.5rem;
      padding: 1rem 1.2rem;
      transition: 0.2s;
      border: 1px solid rgba(100, 150, 255, 0.2);
    }
    .product-card:hover {
      border-color: #b77cff;
      transform: translateY(-3px);
    }
    .product-title {
      font-weight: 800;
      font-size: 1.15rem;
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
    }
    .price {
      color: #facc15;
      font-weight: 800;
    }
    .price-dm {
      color: #2dd4bf;
      font-weight: 700;
      font-size: 0.85rem;
      background: #0a1a2f;
      padding: 2px 8px;
      border-radius: 20px;
    }
    .desc {
      font-size: 0.75rem;
      color: #b9c7ec;
      margin: 6px 0;
    }
    .buy-btn {
      background: #1f2a4a;
      border: none;
      color: white;
      padding: 0.5rem;
      border-radius: 2rem;
      margin-top: 0.7rem;
      width: 100%;
      font-weight: 600;
      cursor: pointer;
      transition: 0.2s;
    }
    .buy-btn:hover {
      background: #2dd4bf;
      color: #0a0f1e;
    }
    .dm-btn {
      background: #3b2a4a;
      border: 1px solid #a855f7;
    }
    .dm-btn:hover {
      background: #a855f7;
    }

    /* admin hidden dot */
    .admin-dot {
      position: fixed;
      bottom: 18px;
      right: 18px;
      width: 14px;
      height: 14px;
      background: #2dd4bf;
      border-radius: 50%;
      cursor: pointer;
      z-index: 999;
      opacity: 0.55;
      box-shadow: 0 0 4px white;
    }

    /* modals */
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      background: rgba(0,0,0,0.85);
      backdrop-filter: blur(6px);
      justify-content: center;
      align-items: center;
      z-index: 1100;
    }
    .modal-card {
      background: #0f172ad9;
      border-radius: 2rem;
      width: 90%;
      max-width: 460px;
      padding: 1.8rem;
      border: 1px solid #5ee0fa;
    }
    .modal-card input, .modal-card select {
      width: 100%;
      padding: 0.7rem;
      margin: 0.6rem 0;
      background: #1e293b;
      border: 1px solid #4f6b9f;
      border-radius: 1rem;
      color: white;
    }
    .flex-btns {
      display: flex;
      gap: 1rem;
      margin-top: 1rem;
    }
    .btn-confirm { background: #10b981; padding: 0.6rem; border-radius: 2rem; font-weight: bold; border: none; color: white; flex:1; cursor: pointer;}
    .btn-cancel { background: #475569; flex:1; cursor: pointer;}
    .upi-qr-area {
      text-align: center;
      background: #fff;
      border-radius: 1.2rem;
      padding: 1rem;
      margin: 1rem 0;
    }
    .qr-placeholder {
      background: #f0f0f0;
      padding: 10px;
      border-radius: 20px;
      font-family: monospace;
      color: black;
    }

    .telegram-btn {
      background: #1e2a47;
      padding: 0.6rem 1.5rem;
      border-radius: 3rem;
      text-decoration: none;
      color: white;
      font-weight: bold;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }
    .support-row {
      display: flex;
      justify-content: center;
      gap: 1rem;
      margin: 2rem 0 1rem;
      flex-wrap: wrap;
    }
    .copyRef {
      background: #2d3e5a;
      padding: 4px 12px;
      border-radius: 40px;
      font-size: 0.75rem;
      cursor: pointer;
    }
    footer {
      text-align: center;
      margin-top: 2.5rem;
      font-size: 0.7rem;
      color: #65749e;
    }
    .price-note {
      font-size: 0.7rem;
      color: #facc15;
      margin-top: 5px;
      text-align: center;
    }
    @media (max-width: 550px) {
      .header { flex-direction: column; align-items: stretch; text-align: center; }
      .wallet-card { text-align: center; }
    }
  </style>
</head>
<body>
<div class="container">
  <div class="header">
    <div class="logo">
      <h1>⚡ HYPEHIVE</h1>
      <p>by Arnav & Aarav | digital vault</p>
    </div>
    <div class="wallet-card">
      <div class="wallet-label">💰 WALLET BALANCE</div>
      <div class="wallet-amount" id="walletDisplay">₹0</div>
      <div class="ref-badge" id="showReferralBtn">🔗 REFER & EARN ₹20</div>
    </div>
  </div>

  <!-- deposit banner -->
  <div class="deposit-section">
    <div class="info-text">💳 UPI / QR deposit — instant wallet top-up</div>
    <button class="btn-deposit" id="openDepositModal">➕ ADD MONEY</button>
  </div>

  <!-- products will be injected via js -->
  <div id="productList"></div>

  <!-- middleman & team section -->
  <div class="support-row">
    <a href="https://t.me/ar9fx" target="_blank" class="telegram-btn">📲 SUPPORT / DM @ar9fx</a>
    <button id="middlemanBtn" class="telegram-btn" style="background:#1f3a4b;">🤝 MIDDLEMAN SERVICE</button>
    <button id="joinTeamBtn" class="telegram-btn" style="background:#2b2f4e;">🔥 JOIN TEAM P7</button>
  </div>
  <footer>🔹 After payment DM @ar9fx with screenshot & order ID 🔹 Middleman available for safe trades 🔹 For custom orders DM for pricing</footer>
</div>

<div class="admin-dot" id="adminDotTrigger"></div>

<!-- MODAL: Deposit UPI/QR -->
<div id="depositModal" class="modal">
  <div class="modal-card">
    <h3 style="margin-bottom:10px">💸 Add Funds to Wallet</h3>
    <div class="upi-qr-area">
      <div style="background:#111; padding:8px; border-radius:20px;">
        <p style="color:#fff">📱 UPI ID: <strong>arnaviscool7@fam</strong></p>
        <p style="font-size:12px; background:#222; padding:8px; border-radius:12px;">Scan QR (demo) or pay to above ID</p>
        <div style="background:#f5f5f5; padding:8px; border-radius:18px; margin-top:8px;">
          <code style="color:#000">[ HYPEHIVE QR ] arnaviscool7@fam</code>
        </div>
      </div>
    </div>
    <input type="number" id="depositAmount" placeholder="Enter amount (₹)" style="width:100%">
    <p style="font-size:12px">✅ After payment, admin will add manually OR auto via admin panel. Contact support.</p>
    <div class="flex-btns">
      <button class="btn-confirm" id="requestDepositBtn">Request (DM Admin)</button>
      <button class="btn-cancel close-modal">Close</button>
    </div>
  </div>
</div>

<!-- ADMIN PANEL (hidden, password protected) -->
<div id="adminModal" class="modal">
  <div class="modal-card">
    <h3>🔐 ADMIN CONTROL (HYPEHIVE)</h3>
    <input type="password" id="adminPass" placeholder="Enter admin password">
    <div id="adminPanelContent" style="display:none; margin-top:15px">
      <label>👤 Username (user ID):</label>
      <input type="text" id="targetUserId" placeholder="Enter username (e.g., default)">
      <label>💰 Add Balance (₹):</label>
      <input type="number" id="addBalanceAmount" placeholder="Amount">
      <button id="executeAddBalance" class="btn-confirm" style="background:#2563eb">➕ Add to User Wallet</button>
      <hr style="margin:12px 0">
      <h4>📊 Store Stats</h4>
      <p id="statsView">Total users: -- | Referral earnings</p>
      <button id="viewHistoryBtn" class="buy-btn" style="background:#2c3e66">📜 View Purchase History</button>
      <pre id="historyLog" style="background:#00000080; padding:8px; font-size:11px; max-height:120px; overflow:auto; margin-top:8px;"></pre>
    </div>
    <div class="flex-btns" style="margin-top:15px">
      <button id="adminLoginBtn" class="btn-confirm">Unlock</button>
      <button class="btn-cancel close-modal">Close</button>
    </div>
  </div>
</div>

<!-- Referral Modal -->
<div id="referralModal" class="modal">
  <div class="modal-card">
    <h3>🔗 REFERRAL SYSTEM</h3>
    <p>Share your code & earn ₹20 per friend (after first purchase)</p>
    <p><strong>Your Referral Code:</strong> <span id="userReferralCode">LOADING</span> <button id="copyReferralBtn" class="copyRef">📋 Copy</button></p>
    <input type="text" id="enterReferralInput" placeholder="Enter friend's referral code (coupon)">
    <button id="applyReferralBtn" class="btn-confirm" style="margin-top:6px">Apply ₹20 Bonus</button>
    <button class="btn-cancel close-modal">Close</button>
  </div>
</div>

<!-- Middleman info modal -->
<div id="middlemanModal" class="modal">
  <div class="modal-card">
    <h3>🤝 MIDDLEMAN SERVICE (Secure Trade)</h3>
    <p>🔹 We provide trusted middleman for any deal (account buying/courses/boosting).<br>
    🔹 Buyer pays to HYPEHIVE wallet/middleman, seller delivers, then funds released.<br>
    🔹 Middleman fee: 5% or min ₹30.<br>
    🔹 For boosting services: DM @ar9fx with requirements - pricing 50-500 depends on type & quantity.<br>
    📲 To initiate: DM @ar9fx with "MIDDLEMAN REQUEST" + deal details.<br>
    ✅ Safe & dispute resolution included.</p>
    <button class="btn-cancel close-modal">Got it</button>
  </div>
</div>

<!-- Team P7 join modal -->
<div id="teamModal" class="modal">
  <div class="modal-card">
    <h3>🔥 JOIN TEAM P7 (HYPEHIVE)</h3>
    <p>Exclusive reseller perks, discounts, and early access. DM @ar9fx with "TEAMP7" and your wallet ID.</p>
    <p>✅ Affiliate commission: 15% on referrals via your code.</p>
    <p>✅ Special wholesale prices on boosting & accounts.</p>
    <button class="btn-cancel close-modal">Close</button>
  </div>
</div>

<script>
  // ---------- STORAGE KEYS ----------
  const STORAGE_USER = "hypehive_user";
  let currentUser = {
    username: "customer_" + Math.floor(Math.random() * 10000),
    balance: 0,
    referralCode: "",
    referredBy: null,
    purchaseHistory: []
  };

  let allUsers = {}; // username -> userData (admin stats)

  function initData() {
    let stored = localStorage.getItem(STORAGE_USER);
    if(stored) {
      try{
        let parsed = JSON.parse(stored);
        currentUser = parsed;
      }catch(e){}
    }
    if(!currentUser.referralCode){
      currentUser.referralCode = "HYPE" + Math.random().toString(36).substring(2,8).toUpperCase();
    }
    if(!currentUser.purchaseHistory) currentUser.purchaseHistory = [];
    if(!currentUser.username) currentUser.username = "user_" + Math.floor(Math.random() * 9999);
    // load all users map from localstorage for admin
    let allUsersRaw = localStorage.getItem("hypehive_all_users");
    if(allUsersRaw) allUsers = JSON.parse(allUsersRaw);
    else allUsers = {};
    if(!allUsers[currentUser.username]) {
      allUsers[currentUser.username] = JSON.parse(JSON.stringify(currentUser));
    } else {
      // sync balance
      currentUser.balance = allUsers[currentUser.username].balance || currentUser.balance;
      currentUser.purchaseHistory = allUsers[currentUser.username].purchaseHistory || [];
      currentUser.referralCode = allUsers[currentUser.username].referralCode || currentUser.referralCode;
    }
    saveAll();
    updateUI();
  }

  function saveAll() {
    allUsers[currentUser.username] = JSON.parse(JSON.stringify(currentUser));
    localStorage.setItem("hypehive_all_users", JSON.stringify(allUsers));
    localStorage.setItem(STORAGE_USER, JSON.stringify(currentUser));
  }

  function updateUI() {
    document.getElementById("walletDisplay").innerText = "₹" + currentUser.balance;
  }

  function addBalance(amount, reason = "admin") {
    if(amount > 0) {
      currentUser.balance += amount;
      currentUser.purchaseHistory.unshift({ type: "deposit", amount, date: new Date().toLocaleString(), note: reason });
      saveAll();
      updateUI();
      return true;
    }
    return false;
  }

  function deductBalance(amount, productName) {
    if(currentUser.balance >= amount) {
      currentUser.balance -= amount;
      currentUser.purchaseHistory.unshift({ type: "purchase", product: productName, amount, date: new Date().toLocaleString() });
      saveAll();
      updateUI();
      return true;
    }
    return false;
  }

  function purchaseItem(name, price) {
    if(price === "DM") {
      window.open(`https://t.me/ar9fx?text=Hi%20I'm%20interested%20in%20${encodeURIComponent(name)}%20-%20Please%20share%20pricing%20and%20details.%20My%20Wallet%20ID:%20${currentUser.username}`, "_blank");
      return false;
    }
    if(deductBalance(price, name)) {
      alert(`✅ Purchased ${name} for ₹${price}. DM @ar9fx with order details.`);
      window.open(`https://t.me/ar9fx?text=Hi%20I%20bought%20${encodeURIComponent(name)}%20for%20₹${price}%20Wallet%20ID%3A${currentUser.username}`, "_blank");
      return true;
    } else {
      alert(`❌ Insufficient balance! Need ₹${price}. Add money via deposit.`);
      return false;
    }
  }

  // Render products
  const productCatalog = [
    // Old accounts
    { name:"📱 IG Acc 2012 (2k12)", price:300, category:"Old Acc", fixed:true},
    { name:"📱 IG Acc 2013", price:250, fixed:true},
    { name:"📱 IG Acc 2014", price:300, fixed:true},
    { name:"📱 IG Acc 2015", price:250, fixed:true},
    { name:"📱 IG Acc 2016", price:200, fixed:true},
    { name:"📱 IG Acc 2017", price:150, fixed:true},
    { name:"📱 IG Acc 2018", price:100, fixed:true},
    { name:"📱 IG Acc 2019", price:70, fixed:true},
    // Courses
    { name:"🎓 Banning + Unbanning Course (1 month)", price:300, desc:"Full unban methods", fixed:true},
    { name:"🎓 Jacking Course", price:200, fixed:true},
    { name:"🐍 Python/Termux Automation", price:100, fixed:true},
    { name:"✂️ Editing Course (Video/Photo)", price:150, fixed:true},
    // Social Media Boosting - DM FOR PRICING
    { name:"📈 Instagram Followers", price:"DM", desc:"50-500 depends on type & quantity • DM for custom package", boost:true},
    { name:"❤️ Instagram Likes", price:"DM", desc:"50-500 depends on type & quantity • DM for pricing", boost:true},
    { name:"📺 YouTube Subscribers", price:"DM", desc:"50-500 depends on type & quantity • DM for pricing", boost:true},
    { name:"👥 Telegram Members", price:"DM", desc:"50-500 depends on type & quantity • DM for pricing", boost:true},
    { name:"🎵 TikTok Followers/Likes", price:"DM", desc:"50-500 depends on type & quantity • DM for pricing", boost:true},
    { name:"🐦 Twitter/X Followers", price:"DM", desc:"50-500 depends on type & quantity • DM for pricing", boost:true},
    { name:"📘 Facebook Followers/Likes", price:"DM", desc:"50-500 depends on type & quantity • DM for pricing", boost:true},
    // Digital services
    { name:"💬 WhatsApp Number (Germany)", price:100, desc:"verified", fixed:true},
    { name:"💬 WhatsApp Number (Pakistan)", price:70, fixed:true},
    { name:"💬 WhatsApp Number (Ivory Coast)", price:50, fixed:true},
    { name:"🌍 International WhatsApp Numbers", price:"DM", desc:"Any country available • DM for pricing", fixed:false},
    { name:"✅ Meta Blue Tick Verification (1 month)", price:300, desc:"official badge", fixed:true},
    { name:"🖼️ Custom Profile Pic (PFP) design", price:10, fixed:true},
    { name:"🔒 Paid Banning Service (per account)", price:"DM", desc:"200-500 depends on account • DM for quote", fixed:false},
    { name:"🛡️ Account Selling (any niche)", price:"DM", desc:"DM with requirements • pricing negotiable", fixed:false},
    { name:"✅ Verified IDs (PAN/DL/Passport)", price:"DM", desc:"Digital verified IDs • DM for pricing", fixed:false}
  ];

  function renderProducts() {
    const grid = document.getElementById("productList");
    grid.innerHTML = `
      <div class="section-title">🛡️ OLD INSTAGRAM ACCOUNTS</div>
      <div class="products-grid" id="oldAccountsGrid"></div>
      <div class="section-title">🎓 PREMIUM COURSES</div>
      <div class="products-grid" id="coursesGrid"></div>
      <div class="section-title">📊 SOCIAL MEDIA BOOSTING</div>
      <div class="price-note">💡 All boosting services: ₹50-500 depending on type, quantity & quality • DM for exact pricing</div>
      <div class="products-grid" id="boostingGrid"></div>
      <div class="section-title">💳 DIGITAL SERVICES & MORE</div>
      <div class="products-grid" id="digitalGrid"></div>
    `;
    
    const oldAccounts = productCatalog.filter(p => p.name.includes("IG Acc"));
    const courses = productCatalog.filter(p => p.name.includes("Course") || p.name.includes("Editing") || p.name.includes("Python") || p.name.includes("Jacking"));
    const boosting = productCatalog.filter(p => p.boost === true || p.name.includes("Followers") || p.name.includes("Likes") || p.name.includes("Subscribers") || p.name.includes("Members") || p.name.includes("TikTok") || p.name.includes("Twitter") || p.name.includes("Facebook"));
    const digital = productCatalog.filter(p => !oldAccounts.includes(p) && !courses.includes(p) && !boosting.includes(p));
    
    function renderGrid(containerId, items) {
      const container = document.getElementById(containerId);
      if(!container) return;
      container.innerHTML = "";
      items.forEach(prod => {
        let card = document.createElement("div");
        card.className = "product-card";
        let priceHtml = (prod.price === "DM") ? 
          `<span class="price-dm">💬 DM for Price</span>` : 
          `<span class="price">₹${prod.price}</span>
