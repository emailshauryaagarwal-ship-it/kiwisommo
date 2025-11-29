<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Kiwisimmo V2</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />

  <style>
    :root {
      --amazon-dark: #131921;
      --amazon-light: #232f3e;
      --amazon-accent: #ff9900;
      --bg-page: #f3f4f6;
      --card-bg: #ffffff;
      --border-soft: #e5e7eb;
      --text-main: #111827;
      --text-muted: #6b7280;
      --danger: #ef4444;
      --success: #16a34a;
    }

    * {
      box-sizing: border-box;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
    }

    body {
      margin: 0;
      background: var(--bg-page);
      color: var(--text-main);
    }

    /* Header / Nav */

    .top-nav {
      background: var(--amazon-dark);
      color: #f9fafb;
      padding: 8px 16px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      flex-wrap: wrap;
    }

    .nav-left {
      display: flex;
      align-items: center;
      gap: 10px;
    }

    .logo-box {
      background: #232f3e;
      border-radius: 4px;
      padding: 4px 8px;
      display: flex;
      align-items: baseline;
      gap: 4px;
    }

    .logo-main {
      font-size: 1rem;
      font-weight: 700;
      letter-spacing: 0.05em;
      text-transform: uppercase;
      color: #f9fafb;
    }

    .logo-sub {
      font-size: 0.75rem;
      color: #d1d5db;
    }

    .nav-search {
      flex: 1;
      max-width: 420px;
      display: flex;
      align-items: stretch;
      border-radius: 6px;
      overflow: hidden;
      background: #f9fafb;
    }

    .nav-search input {
      border: none;
      padding: 7px 9px;
      flex: 1;
      font-size: 0.85rem;
      outline: none;
    }

    .nav-search button {
      border: none;
      background: var(--amazon-accent);
      color: #111827;
      font-size: 0.85rem;
      padding: 0 12px;
      cursor: pointer;
      font-weight: 600;
    }

    .nav-right {
      display: flex;
      align-items: center;
      gap: 10px;
      flex-wrap: wrap;
    }

    .user-badge {
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 0.8rem;
      background: #111827;
      padding: 5px 9px;
      border-radius: 16px;
    }

    .avatar {
      width: 24px;
      height: 24px;
      border-radius: 999px;
      background: #f59e0b;
      color: #111827;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 0.85rem;
      font-weight: 700;
    }

    .points-chip {
      background: #064e3b;
      color: #bbf7d0;
      padding: 4px 7px;
      border-radius: 999px;
      font-size: 0.75rem;
    }

    .logout-btn {
      border: 1px solid #e5e7eb;
      border-radius: 16px;
      padding: 4px 9px;
      font-size: 0.75rem;
      cursor: pointer;
      background: #111827;
      color: #f9fafb;
    }

    .login-pill {
      border-radius: 16px;
      border: 1px solid #9ca3af;
      padding: 4px 9px;
      font-size: 0.8rem;
      color: #e5e7eb;
    }

    /* Layout */

    .layout {
      display: grid;
      grid-template-columns: minmax(0, 0.9fr) minmax(0, 2fr);
      gap: 16px;
      padding: 16px;
      max-width: 1200px;
      margin: 0 auto;
    }

    @media (max-width: 840px) {
      .layout {
        grid-template-columns: minmax(0, 1fr);
      }
    }

    .card {
      background: var(--card-bg);
      border-radius: 8px;
      border: 1px solid var(--border-soft);
      padding: 14px 16px;
      box-shadow: 0 1px 2px rgba(15, 23, 42, 0.08);
    }

    .card h2 {
      margin: 0 0 8px;
      font-size: 1rem;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .card h3 {
      margin: 10px 0 6px;
      font-size: 0.95rem;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .caption {
      margin: 0 0 10px;
      font-size: 0.8rem;
      color: var(--text-muted);
    }

    label {
      display: block;
      font-size: 0.78rem;
      margin-bottom: 3px;
      color: var(--text-muted);
    }

    input, textarea, select {
      width: 100%;
      padding: 7px 9px;
      font-size: 0.85rem;
      border-radius: 4px;
      border: 1px solid #d1d5db;
      outline: none;
    }

    input:focus, textarea:focus, select:focus {
      border-color: var(--amazon-accent);
      box-shadow: 0 0 0 1px rgba(245, 158, 11, 0.5);
    }

    textarea {
      resize: vertical;
      min-height: 70px;
    }

    .field {
      margin-bottom: 8px;
    }

    .role-toggle {
      display: flex;
      border-radius: 20px;
      border: 1px solid #d1d5db;
      overflow: hidden;
      margin-bottom: 10px;
    }

    .role-chip {
      flex: 1;
      padding: 6px 8px;
      font-size: 0.8rem;
      text-align: center;
      cursor: pointer;
      background: #f9fafb;
      color: var(--text-muted);
    }

    .role-chip.active {
      background: var(--amazon-accent);
      color: #111827;
      font-weight: 600;
    }

    .pill-info {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-size: 0.75rem;
      padding: 4px 8px;
      border-radius: 999px;
      border: 1px dashed #9ca3af;
      color: var(--text-muted);
      margin-bottom: 8px;
    }

    .btn-row {
      display: flex;
      gap: 8px;
      flex-wrap: wrap;
      margin-top: 6px;
    }

    button.primary {
      border: none;
      background: var(--amazon-accent);
      color: #111827;
      padding: 7px 12px;
      font-size: 0.85rem;
      border-radius: 4px;
      cursor: pointer;
      font-weight: 600;
    }

    button.secondary {
      border: 1px solid #d1d5db;
      background: #f9fafb;
      color: #111827;
      padding: 7px 12px;
      font-size: 0.85rem;
      border-radius: 4px;
      cursor: pointer;
    }

    button.small {
      padding: 3px 7px;
      font-size: 0.75rem;
    }

    button.danger {
      border-color: var(--danger);
      color: var(--danger);
    }

    .msg-error, .msg-success {
      font-size: 0.78rem;
      margin-bottom: 6px;
      padding: 6px 8px;
      border-radius: 4px;
      display: none;
    }

    .msg-error {
      background: #fee2e2;
      color: #b91c1c;
      border: 1px solid #fecaca;
    }

    .msg-success {
      background: #dcfce7;
      color: #166534;
      border: 1px solid #bbf7d0;
    }

    .hidden {
      display: none !important;
    }

    /* Tabs / main panel */

    .tabs {
      display: flex;
      gap: 6px;
      border-bottom: 1px solid #e5e7eb;
      margin-bottom: 10px;
      flex-wrap: wrap;
    }

    .tab-btn {
      padding: 6px 9px;
      border-radius: 4px 4px 0 0;
      font-size: 0.8rem;
      cursor: pointer;
      border: 1px solid transparent;
      background: transparent;
      color: var(--text-muted);
    }

    .tab-btn.active {
      border-color: #e5e7eb #e5e7eb #ffffff;
      background: #ffffff;
      color: #111827;
      font-weight: 600;
    }

    .tab-panel {
      display: none;
    }

    .tab-panel.active {
      display: block;
    }

    .two-cols {
      display: grid;
      grid-template-columns: minmax(0,1.2fr) minmax(0,1.2fr);
      gap: 12px;
    }

    @media (max-width: 840px) {
      .two-cols {
        grid-template-columns: minmax(0,1fr);
      }
    }

    .scroll-box {
      max-height: 230px;
      overflow-y: auto;
      padding-right: 4px;
      border: 1px solid #e5e7eb;
      border-radius: 4px;
      background: #f9fafb;
    }

    .scroll-box-inner {
      padding: 8px;
    }

    /* Notices */

    .notice-card {
      border-radius: 4px;
      border: 1px solid #e5e7eb;
      background: #ffffff;
      padding: 6px 8px;
      margin-bottom: 6px;
      font-size: 0.8rem;
    }

    .notice-title {
      font-weight: 600;
      margin-bottom: 2px;
    }

    .notice-meta {
      font-size: 0.7rem;
      color: #6b7280;
      margin-top: 2px;
    }

    /* Market */

    .item-card {
      border-radius: 4px;
      border: 1px solid #e5e7eb;
      background: #ffffff;
      padding: 6px 8px;
      margin-bottom: 6px;
      font-size: 0.8rem;
    }

    .item-header {
      display: flex;
      justify-content: space-between;
      gap: 6px;
    }

    .item-title {
      font-weight: 600;
    }

    .badge {
      display: inline-block;
      border-radius: 999px;
      padding: 2px 7px;
      font-size: 0.7rem;
      border: 1px solid #d1d5db;
      margin-top: 3px;
    }

    .badge-green {
      border-color: #16a34a;
      color: #166534;
    }

    .badge-gray {
      color: #4b5563;
    }

    .item-footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 4px;
    }

    .price-tag {
      font-weight: 700;
      color: #b45309;
    }

    .sold {
      opacity: 0.6;
    }

    /* Users / admin */

    table {
      width: 100%;
      border-collapse: collapse;
      font-size: 0.78rem;
    }

    th, td {
      border-bottom: 1px solid #e5e7eb;
      padding: 4px 6px;
      text-align: left;
    }

    th {
      color: #6b7280;
      font-weight: 500;
    }

    /* Chat & DMs */

    .chat-message {
      border-radius: 4px;
      border: 1px solid #e5e7eb;
      background: #ffffff;
      padding: 4px 6px;
      margin-bottom: 5px;
      font-size: 0.8rem;
    }

    .chat-meta-row {
      display: flex;
      justify-content: space-between;
      font-size: 0.7rem;
      color: #6b7280;
      margin-bottom: 2px;
    }

    .chat-from-mgmt {
      border-left: 3px solid #f97316;
    }

    .chat-self {
      border-left: 3px solid #22c55e;
    }

    .dm-layout {
      display: grid;
      grid-template-columns: 140px minmax(0,1fr);
      gap: 8px;
    }

    @media (max-width: 780px) {
      .dm-layout {
        grid-template-columns: minmax(0,1fr);
      }
    }

    .dm-user-list {
      border: 1px solid #e5e7eb;
      border-radius: 4px;
      background: #f9fafb;
      max-height: 220px;
      overflow-y: auto;
      font-size: 0.8rem;
    }

    .dm-user {
      padding: 6px 8px;
      cursor: pointer;
      border-bottom: 1px solid #e5e7eb;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .dm-user.active {
      background: #e5e7eb;
      font-weight: 600;
    }

    .badge-role {
      border-radius: 999px;
      border: 1px solid #9ca3af;
      padding: 1px 5px;
      font-size: 0.65rem;
      color: #4b5563;
    }

    /* Leaderboard */

    .lb-tag {
      border-radius: 999px;
      padding: 2px 6px;
      font-size: 0.7rem;
      border: 1px solid #d1d5db;
      margin-right: 4px;
    }

    .badge-pill {
      border-radius: 999px;
      padding: 2px 6px;
      font-size: 0.7rem;
      border: 1px solid #d1d5db;
      margin: 1px 3px 1px 0;
      display: inline-block;
    }

    .badge-pill-gold {
      border-color: #fbbf24;
      color: #92400e;
    }

    .badge-pill-green {
      border-color: #22c55e;
      color: #166534;
    }

    .badge-pill-blue {
      border-color: #3b82f6;
      color: #1d4ed8;
    }

    /* Toasts */

    .toast-container {
      position: fixed;
      right: 10px;
      bottom: 10px;
      z-index: 50;
      max-width: 260px;
    }

    .toast {
      background: #111827;
      color: #f9fafb;
      padding: 7px 10px;
      border-radius: 4px;
      margin-top: 6px;
      font-size: 0.8rem;
      box-shadow: 0 4px 8px rgba(15, 23, 42, 0.3);
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 8px;
    }

    .toast.success {
      border-left: 4px solid #22c55e;
    }

    .toast.error {
      border-left: 4px solid #ef4444;
    }

    .toast button {
      background: transparent;
      border: none;
      color: #9ca3af;
      cursor: pointer;
      font-size: 0.8rem;
    }
  </style>
</head>
<body>

<!-- Top nav -->
<header class="top-nav">
  <div class="nav-left">
    <div class="logo-box">
      <div class="logo-main">Kiwisimmo</div>
      <div class="logo-sub">points marketplace</div>
    </div>
  </div>

  <div class="nav-search">
    <input type="text" placeholder="Search (visual only, no logic yet)" />
    <button>Search</button>
  </div>

  <div class="nav-right" id="navRightLoggedOut">
    <span class="login-pill">Not logged in</span>
  </div>

  <div class="nav-right hidden" id="navRightUser">
    <div class="user-badge">
      <div class="avatar" id="navAvatar">U</div>
      <div>
        <div id="navUserName" style="font-size:0.8rem;">User</div>
        <div id="navUserRole" style="font-size:0.7rem;color:#9ca3af;">Role</div>
      </div>
      <div class="points-chip" id="navPoints">💎 0 pts</div>
    </div>
    <button class="logout-btn" id="logoutBtn">Logout</button>
  </div>
</header>

<div class="layout">
  <!-- Left: Auth -->
  <section class="card">
    <h2>Sign in or create account</h2>
    <p class="caption">
      Choose role and log in. Management uses fixed credentials; civilians create accounts.
    </p>

    <div class="role-toggle">
      <div class="role-chip active" data-role="civilian">Civilian</div>
      <div class="role-chip" data-role="management">Management</div>
    </div>

    <div class="pill-info">
      Management: <code>Goat_201455 / 676767</code>
    </div>

    <div id="authError" class="msg-error"></div>
    <div id="authSuccess" class="msg-success"></div>

    <!-- Civilian auth -->
    <div id="civilianAuthSection">
      <div class="field">
        <label for="civUsername">Username</label>
        <input id="civUsername" type="text" placeholder="Choose a username" />
      </div>
      <div class="field">
        <label for="civPassword">Password</label>
        <input id="civPassword" type="password" placeholder="Create a password" />
      </div>
      <div class="btn-row">
        <button class="primary" id="btnCivLogin">Log in</button>
        <button class="secondary" id="btnCivSignup">Create account</button>
      </div>
    </div>

    <!-- Management auth -->
    <div id="managementAuthSection" class="hidden">
      <div class="field">
        <label for="mgmtUsername">Management username</label>
        <input id="mgmtUsername" type="text" placeholder="Goat_201455" />
      </div>
      <div class="field">
        <label for="mgmtPassword">Management password</label>
        <input id="mgmtPassword" type="password" placeholder="676767" />
      </div>
      <div class="btn-row">
        <button class="primary" id="btnMgmtLogin">Log in as management</button>
      </div>
    </div>

    <hr style="margin:14px 0;border:none;border-top:1px solid #e5e7eb;" />

    <h3>Quick help</h3>
    <p class="caption">
      • Civilians: trade items using points, chat, DM, climb the leaderboard.<br />
      • Management: publish notices, edit points, ban users, join chat & DMs.
    </p>
  </section>

  <!-- Right: Main app -->
  <section class="card">
    <div id="mainLocked">
      <h2>Welcome to Kiwisimmo</h2>
      <p class="caption">
        Sign in on the left to access the marketplace, notices, chat, DMs and leaderboard.
      </p>
    </div>

    <div id="mainApp" class="hidden">
      <nav class="tabs">
        <button class="tab-btn active" data-tab="marketTab">Market</button>
        <button class="tab-btn" data-tab="noticesTab">Notices</button>
        <button class="tab-btn" data-tab="chatTab">Global chat</button>
        <button class="tab-btn" data-tab="dmTab">DMs</button>
        <button class="tab-btn" data-tab="leaderTab">Leaderboard</button>
        <button class="tab-btn" data-tab="adminTab" id="adminTabBtn">Admin</button>
      </nav>

      <!-- Market tab -->
      <div class="tab-panel active" id="marketTab">
        <h3>Marketplace</h3>
        <p class="caption">
          Civilians can list items for points; other civilians can buy them.
        </p>
        <div class="two-cols">
          <div>
            <h4 style="margin:0 0 4px;font-size:0.9rem;">Create listing (civilian)</h4>
            <div id="marketMsg" class="msg-error"></div>
            <div class="field">
              <label for="itemTitle">Item title</label>
              <input id="itemTitle" type="text" placeholder="E.g. Rare digital kiwi badge" />
            </div>
            <div class="field">
              <label for="itemCategory">Category</label>
              <select id="itemCategory">
                <option value="Collectible">Collectible</option>
                <option value="Art">Art</option>
                <option value="Boost">Boost</option>
                <option value="Other">Other</option>
              </select>
            </div>
            <div class="field">
              <label for="itemDesc">Description</label>
              <textarea id="itemDesc" placeholder="Describe your item..."></textarea>
            </div>
            <div class="field">
              <label for="itemPrice">Price (points)</label>
              <input id="itemPrice" type="number" min="1" placeholder="50" />
            </div>
            <div class="btn-row">
              <button class="primary" id="btnCreateItem">List item</button>
            </div>
          </div>

          <div>
            <h4 style="margin:0 0 4px;font-size:0.9rem;">Browse listings</h4>
            <div class="scroll-box">
              <div class="scroll-box-inner" id="marketList"></div>
            </div>
          </div>
        </div>
      </div>

      <!-- Notices tab -->
      <div class="tab-panel" id="noticesTab">
        <h3>Notices</h3>
        <p class="caption">
          Civilians can read notices; only management can post new ones.
        </p>
        <div class="two-cols">
          <div>
            <h4 style="margin:0 0 4px;font-size:0.9rem;">All notices</h4>
            <div class="scroll-box">
              <div class="scroll-box-inner" id="noticesList"></div>
            </div>
          </div>
          <div id="noticeFormWrapper">
            <h4 style="margin:0 0 4px;font-size:0.9rem;">Post notice (management)</h4>
            <div id="noticeMsg" class="msg-success"></div>
            <div class="field">
              <label for="noticeTitle">Title</label>
              <input id="noticeTitle" type="text" placeholder="Maintenance, update, rules..." />
            </div>
            <div class="field">
              <label for="noticeBody">Message</label>
              <textarea id="noticeBody" placeholder="Write the full message..."></textarea>
            </div>
            <button class="primary" id="btnPostNotice">Publish</button>
          </div>
        </div>
      </div>

      <!-- Chat tab -->
      <div class="tab-panel" id="chatTab">
        <h3>Global chat</h3>
        <p class="caption">
          Public room for civilians and management. Everyone sees all messages.
        </p>
        <div class="scroll-box">
          <div class="scroll-box-inner" id="chatMessages"></div>
        </div>
        <div class="btn-row" style="margin-top:8px;">
          <div style="flex:1;">
            <input id="chatInput" type="text" placeholder="Type a message and press Enter..." />
          </div>
          <button class="primary" id="btnChatSend">Send</button>
        </div>
      </div>

      <!-- DM tab -->
      <div class="tab-panel" id="dmTab">
        <h3>Direct messages</h3>
        <p class="caption">
          Chat privately with other users. Civilians can DM management; management can DM any civilian.
        </p>
        <div class="dm-layout">
          <div>
            <div class="dm-user-list" id="dmUserList"></div>
          </div>
          <div>
            <div class="scroll-box">
              <div class="scroll-box-inner" id="dmMessages"></div>
            </div>
            <div class="btn-row" style="margin-top:8px;">
              <div style="flex:1;">
                <input id="dmInput" type="text" placeholder="Select a user, then type message..." />
              </div>
              <button class="primary" id="btnDmSend">Send</button>
            </div>
          </div>
        </div>
      </div>

      <!-- Leaderboard tab -->
      <div class="tab-panel" id="leaderTab">
        <h3>Leaderboard & badges</h3>
        <p class="caption">
          Rankings are based on points and activity. Badges unlock automatically.
        </p>
        <div class="two-cols">
          <div>
            <h4 style="margin:0 0 4px;font-size:0.9rem;">Top by points</h4>
            <div class="scroll-box">
              <div class="scroll-box-inner">
                <table id="lbPointsTable">
                  <thead>
                    <tr>
                      <th>#</th>
                      <th>User</th>
                      <th>Points</th>
                      <th>Badges</th>
                    </tr>
                  </thead>
                  <tbody></tbody>
                </table>
              </div>
            </div>
          </div>
          <div>
            <h4 style="margin:0 0 4px;font-size:0.9rem;">Top sellers</h4>
            <div class="scroll-box">
              <div class="scroll-box-inner">
                <table id="lbSellersTable">
                  <thead>
                    <tr>
                      <th>#</th>
                      <th>User</th>
                      <th>Sold</th>
                      <th>Badges</th>
                    </tr>
                  </thead>
                  <tbody></tbody>
                </table>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Admin tab -->
      <div class="tab-panel" id="adminTab">
        <h3>Admin tools</h3>
        <p class="caption">
          Management only: ban users, edit points and view basic stats.
        </p>
        <div class="scroll-box">
          <div class="scroll-box-inner">
            <table id="adminUsersTable">
              <thead>
                <tr>
                  <th>User</th>
                  <th>Status</th>
                  <th>Points</th>
                  <th>Sold</th>
                  <th>Bought</th>
                  <th>Badges</th>
                  <th>Actions</th>
                </tr>
              </thead>
              <tbody></tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </section>
</div>

<div class="toast-container" id="toastContainer"></div>

<script>
  // ---------- localStorage keys ----------
  const DB_KEYS = {
    USERS: "kiwi_users_v2",
    ITEMS: "kiwi_items_v2",
    NOTICES: "kiwi_notices_v2",
    CHAT: "kiwi_chat_v2",
    DMS: "kiwi_dms_v2"
  };

  function loadArray(key) {
    try {
      const raw = localStorage.getItem(key);
      return raw ? JSON.parse(raw) : [];
    } catch {
      return [];
    }
  }

  function saveArray(key, arr) {
    localStorage.setItem(key, JSON.stringify(arr));
  }

  function findUser(username) {
    const users = loadArray(DB_KEYS.USERS);
    return users.find(
      u => u.username.toLowerCase() === username.toLowerCase()
    );
  }

  function saveUser(user) {
    const users = loadArray(DB_KEYS.USERS);
    const idx = users.findIndex(
      u => u.username.toLowerCase() === user.username.toLowerCase()
    );
    if (idx >= 0) {
      users[idx] = user;
    } else {
      users.push(user);
    }
    saveArray(DB_KEYS.USERS, users);
  }

  // ---------- toast notifications ----------
  const toastContainer = document.getElementById("toastContainer");
  function showToast(message, type = "success") {
    const div = document.createElement("div");
    div.className = "toast " + type;
    div.innerHTML = `
      <span>${message}</span>
      <button>&times;</button>
    `;
    const closeBtn = div.querySelector("button");
    closeBtn.addEventListener("click", () => div.remove());
    toastContainer.appendChild(div);
    setTimeout(() => {
      if (div.parentElement) div.remove();
    }, 3500);
  }

  // ---------- session ----------
  const MGMT_USERNAME = "Goat_201455";
  const MGMT_PASSWORD = "676767";

  let currentSession = {
    username: null,
    role: null // "civilian" or "management"
  };

  // ---------- DOM refs ----------
  const navRightLoggedOut = document.getElementById("navRightLoggedOut");
  const navRightUser = document.getElementById("navRightUser");
  const navAvatar = document.getElementById("navAvatar");
  const navUserName = document.getElementById("navUserName");
  const navUserRole = document.getElementById("navUserRole");
  const navPoints = document.getElementById("navPoints");
  const logoutBtn = document.getElementById("logoutBtn");

  const mainLocked = document.getElementById("mainLocked");
  const mainApp = document.getElementById("mainApp");
  const adminTabBtn = document.getElementById("adminTabBtn");

  const roleChips = document.querySelectorAll(".role-chip");
  const civilianAuthSection = document.getElementById("civilianAuthSection");
  const managementAuthSection = document.getElementById("managementAuthSection");
  const authError = document.getElementById("authError");
  const authSuccess = document.getElementById("authSuccess");

  const civUsernameInput = document.getElementById("civUsername");
  const civPasswordInput = document.getElementById("civPassword");
  const btnCivLogin = document.getElementById("btnCivLogin");
  const btnCivSignup = document.getElementById("btnCivSignup");

  const mgmtUsernameInput = document.getElementById("mgmtUsername");
  const mgmtPasswordInput = document.getElementById("mgmtPassword");
  const btnMgmtLogin = document.getElementById("btnMgmtLogin");

  const tabButtons = document.querySelectorAll(".tab-btn");
  const tabPanels = document.querySelectorAll(".tab-panel");

  // Market
  const marketMsg = document.getElementById("marketMsg");
  const itemTitleInput = document.getElementById("itemTitle");
  const itemCategoryInput = document.getElementById("itemCategory");
  const itemDescInput = document.getElementById("itemDesc");
  const itemPriceInput = document.getElementById("itemPrice");
  const btnCreateItem = document.getElementById("btnCreateItem");
  const marketList = document.getElementById("marketList");

  // Notices
  const noticesList = document.getElementById("noticesList");
  const noticeFormWrapper = document.getElementById("noticeFormWrapper");
  const noticeTitleInput = document.getElementById("noticeTitle");
  const noticeBodyInput = document.getElementById("noticeBody");
  const btnPostNotice = document.getElementById("btnPostNotice");
  const noticeMsg = document.getElementById("noticeMsg");

  // Chat
  const chatMessages = document.getElementById("chatMessages");
  const chatInput = document.getElementById("chatInput");
  const btnChatSend = document.getElementById("btnChatSend");

  // DMs
  const dmUserList = document.getElementById("dmUserList");
  const dmMessages = document.getElementById("dmMessages");
  const dmInput = document.getElementById("dmInput");
  const btnDmSend = document.getElementById("btnDmSend");
  let currentDmTarget = null; // username or "Management"

  // Leaderboard
  const lbPointsTableBody = document.querySelector("#lbPointsTable tbody");
  const lbSellersTableBody = document.querySelector("#lbSellersTable tbody");

  // Admin
  const adminUsersTableBody = document.querySelector("#adminUsersTable tbody");

  // ---------- helpers ----------
  function setAuthMessage(el, msg) {
    el.textContent = msg;
    el.style.display = msg ? "block" : "none";
  }

  function refreshNav() {
    if (currentSession.username) {
      navRightLoggedOut.classList.add("hidden");
      navRightUser.classList.remove("hidden");
      navAvatar.textContent = currentSession.username.charAt(0).toUpperCase();
      navUserName.textContent = currentSession.username;
      navUserRole.textContent =
        currentSession.role === "management" ? "Management" : "Civilian";
      const u = findUser(currentSession.username);
      const pts = currentSession.role === "civilian" ? (u?.points ?? 100) : 0;
      navPoints.textContent =
        currentSession.role === "civilian" ? `💎 ${pts} pts` : "Mgmt";
    } else {
      navRightLoggedOut.classList.remove("hidden");
      navRightUser.classList.add("hidden");
    }
  }

  function refreshMainAccess() {
    if (currentSession.username) {
      mainLocked.classList.add("hidden");
      mainApp.classList.remove("hidden");
      if (currentSession.role === "management") {
        adminTabBtn.classList.remove("hidden");
        noticeFormWrapper.classList.remove("hidden");
      } else {
        adminTabBtn.classList.add("hidden");
        noticeFormWrapper.classList.add("hidden");
      }
    } else {
      mainLocked.classList.remove("hidden");
      mainApp.classList.add("hidden");
    }
  }

  function getOrInitStats(user) {
    if (!user.stats) {
      user.stats = { sold: 0, bought: 0, spent: 0, earned: 0 };
    }
    return user.stats;
  }

  function ensureBadgesArray(user) {
    if (!Array.isArray(user.badges)) user.badges = [];
  }

  function addBadge(user, badge) {
    ensureBadgesArray(user);
    if (!user.badges.includes(badge)) {
      user.badges.push(badge);
    }
  }

  function updateBadgesForUser(user) {
    ensureBadgesArray(user);
    const stats = getOrInitStats(user);
    const pts = user.points ?? 100;

    if (stats.bought + stats.sold >= 1) addBadge(user, "First Trade");
    if (stats.spent >= 200) addBadge(user, "Big Spender");
    if (stats.sold >= 5) addBadge(user, "Trusted Seller");
    if (pts >= 500) addBadge(user, "High Roller");
    if (stats.bought >= 5) addBadge(user, "Collector");

    saveUser(user);
  }

  // ---------- role toggle ----------
  roleChips.forEach(chip => {
    chip.addEventListener("click", () => {
      roleChips.forEach(c => c.classList.remove("active"));
      chip.classList.add("active");
      if (chip.dataset.role === "civilian") {
        civilianAuthSection.classList.remove("hidden");
        managementAuthSection.classList.add("hidden");
      } else {
        civilianAuthSection.classList.add("hidden");
        managementAuthSection.classList.remove("hidden");
      }
      setAuthMessage(authError, "");
      setAuthMessage(authSuccess, "");
    });
  });

  // ---------- auth: civilian ----------
  btnCivSignup.addEventListener("click", () => {
    setAuthMessage(authError, "");
    setAuthMessage(authSuccess, "");

    const username = civUsernameInput.value.trim();
    const password = civPasswordInput.value.trim();

    if (!username || !password) {
      setAuthMessage(authError, "Enter both username and password.");
      return;
    }
    if (findUser(username)) {
      setAuthMessage(authError, "That username is already taken.");
      return;
    }

    const user = {
      username,
      password,
      role: "civilian",
      points: 100,
      banned: false,
      joinedAt: new Date().toISOString(),
      stats: { sold: 0, bought: 0, spent: 0, earned: 0 },
      badges: ["Newcomer"]
    };

    saveUser(user);
    setAuthMessage(authSuccess, "Account created. You can now log in.");
    showToast("Civilian account created", "success");
  });

  btnCivLogin.addEventListener("click", () => {
    setAuthMessage(authError, "");
    setAuthMessage(authSuccess, "");

    const username = civUsernameInput.value.trim();
    const password = civPasswordInput.value.trim();
    if (!username || !password) {
      setAuthMessage(authError, "Enter both username and password.");
      return;
    }
    const user = findUser(username);
    if (!user || user.password !== password || user.role !== "civilian") {
      setAuthMessage(authError, "Invalid civilian credentials.");
      return;
    }
    if (user.banned) {
      setAuthMessage(authError, "Account banned by management.");
      return;
    }

    currentSession.username = user.username;
    currentSession.role = "civilian";
    setAuthMessage(authSuccess, "Logged in as civilian.");
    showToast("Welcome back, " + user.username, "success");
    afterLogin();
  });

  // ---------- auth: management ----------
  btnMgmtLogin.addEventListener("click", () => {
    setAuthMessage(authError, "");
    setAuthMessage(authSuccess, "");

    const username = mgmtUsernameInput.value.trim();
    const password = mgmtPasswordInput.value.trim();
    if (!username || !password) {
      setAuthMessage(authError, "Enter username and password.");
      return;
    }
    if (username === MGMT_USERNAME && password === MGMT_PASSWORD) {
      currentSession.username = MGMT_USERNAME;
      currentSession.role = "management";
      setAuthMessage(authSuccess, "Logged in as management.");
      showToast("Management session started", "success");
      afterLogin();
    } else {
      setAuthMessage(authError, "Invalid management credentials.");
    }
  });

  // ---------- logout ----------
  logoutBtn.addEventListener("click", () => {
    currentSession.username = null;
    currentSession.role = null;
    refreshNav();
    refreshMainAccess();
    showToast("Logged out", "success");
  });

  function afterLogin() {
    refreshNav();
    refreshMainAccess();
    renderNotices();
    renderMarket();
    renderChat();
    rebuildDmUserList();
    renderDmMessages();
    renderLeaderboards();
    renderAdminTable();
  }

  // ---------- tabs ----------
  tabButtons.forEach(btn => {
    btn.addEventListener("click", () => {
      const tab = btn.dataset.tab;
      tabButtons.forEach(b => b.classList.remove("active"));
      btn.classList.add("active");
      tabPanels.forEach(p => {
        if (p.id === tab) p.classList.add("active");
        else p.classList.remove("active");
      });

      // refresh specific views when switching
      if (tab === "leaderTab") renderLeaderboards();
      if (tab === "adminTab") renderAdminTable();
      if (tab === "dmTab") {
        rebuildDmUserList();
        renderDmMessages();
      }
    });
  });

  // ---------- notices ----------
  function renderNotices() {
    const notices = loadArray(DB_KEYS.NOTICES).sort(
      (a, b) => new Date(b.createdAt) - new Date(a.createdAt)
    );
    if (!notices.length) {
      noticesList.innerHTML =
        '<p class="caption">No notices yet. Management will post updates here.</p>';
      return;
    }
    noticesList.innerHTML = "";
    notices.forEach(n => {
      const div = document.createElement("div");
      div.className = "notice-card";
      const dateStr = new Date(n.createdAt).toLocaleString();
      div.innerHTML = `
        <div class="notice-title">${n.title}</div>
        <div>${n.body}</div>
        <div class="notice-meta">${dateStr} • Management</div>
      `;
      noticesList.appendChild(div);
    });
  }

  btnPostNotice.addEventListener("click", () => {
    if (currentSession.role !== "management") {
      showToast("Only management can post notices", "error");
      return;
    }
    const title = noticeTitleInput.value.trim();
    const body = noticeBodyInput.value.trim();
    if (!title || !body) {
      noticeMsg.classList.remove("msg-success");
      noticeMsg.classList.add("msg-error");
      setAuthMessage(noticeMsg, "Title and message required.");
      return;
    }
    const notices = loadArray(DB_KEYS.NOTICES);
    notices.push({
      id: Date.now(),
      title,
      body,
      createdAt: new Date().toISOString()
    });
    saveArray(DB_KEYS.NOTICES, notices);
    noticeTitleInput.value = "";
    noticeBodyInput.value = "";
    noticeMsg.classList.remove("msg-error");
    noticeMsg.classList.add("msg-success");
    setAuthMessage(noticeMsg, "Notice published.");
    showToast("Notice published", "success");
    renderNotices();
  });

  // ---------- market ----------
  function renderMarket() {
    const items = loadArray(DB_KEYS.ITEMS).sort(
      (a, b) => new Date(b.createdAt) - new Date(a.createdAt)
    );
    if (!items.length) {
      marketList.innerHTML =
        '<p class="caption">No items listed yet. Be the first to list something!</p>';
      return;
    }
    marketList.innerHTML = "";
    items.forEach(item => {
      const div = document.createElement("div");
      div.className = "item-card" + (item.status === "sold" ? " sold" : "");
      const priceText = `${item.price} pts`;
      const statusText =
        item.status === "sold"
          ? `Sold${item.buyer ? " to " + item.buyer : ""}`
          : "For sale";
      div.innerHTML = `
        <div class="item-header">
          <div>
            <div class="item-title">${item.title}</div>
            <div class="caption">Seller: ${item.owner}</div>
          </div>
          <div class="price-tag">💎 ${priceText}</div>
        </div>
        <div class="caption">Category: ${item.category}</div>
        <div style="font-size:0.8rem;margin-top:2px;">${item.desc}</div>
        <div class="item-footer">
          <div>
            <span class="badge badge-gray">${statusText}</span>
          </div>
          <div>
            ${
              item.status !== "sold" &&
              currentSession.role === "civilian" &&
              currentSession.username !== item.owner
                ? '<button class="primary small buy-btn">Buy</button>'
                : ""
            }
          </div>
        </div>
      `;
      if (
        item.status !== "sold" &&
        currentSession.role === "civilian" &&
        currentSession.username !== item.owner
      ) {
        const buyBtn = div.querySelector(".buy-btn");
        buyBtn.addEventListener("click", () => handleBuy(item.id));
      }
      marketList.appendChild(div);
    });
  }

  btnCreateItem.addEventListener("click", () => {
    marketMsg.style.display = "none";
    const title = itemTitleInput.value.trim();
    const category = itemCategoryInput.value;
    const desc = itemDescInput.value.trim();
    const price = Number(itemPriceInput.value.trim());

    if (!currentSession.username || currentSession.role !== "civilian") {
      marketMsg.textContent = "You must be logged in as a civilian to list items.";
      marketMsg.style.display = "block";
      return;
    }

    if (!title || !desc || !price || price <= 0) {
      marketMsg.textContent = "Fill all fields with a valid price.";
      marketMsg.style.display = "block";
      return;
    }

    const items = loadArray(DB_KEYS.ITEMS);
    items.push({
      id: Date.now(),
      title,
      desc,
      price,
      category,
      owner: currentSession.username,
      status: "for sale",
      buyer: null,
      createdAt: new Date().toISOString()
    });
    saveArray(DB_KEYS.ITEMS, items);
    itemTitleInput.value = "";
    itemDescInput.value = "";
    itemPriceInput.value = "";
    showToast("Item listed", "success");
    renderMarket();
  });

  function handleBuy(itemId) {
    if (!currentSession.username || currentSession.role !== "civilian") {
      showToast("Only civilians can buy items", "error");
      return;
    }
    const items = loadArray(DB_KEYS.ITEMS);
    const idx = items.findIndex(i => i.id === itemId);
    if (idx < 0) return;
    const item = items[idx];
    if (item.status === "sold") {
      showToast("Item already sold", "error");
      return;
    }

    const buyer = findUser(currentSession.username);
    if (!buyer || buyer.banned) {
      showToast("Account banned or not found", "error");
      return;
    }
    const price = Number(item.price);
    if ((buyer.points ?? 0) < price) {
      showToast("Not enough points", "error");
      return;
    }

    // seller
    const seller = findUser(item.owner);
    // update buyer
    buyer.points = (buyer.points ?? 0) - price;
    const buyerStats = getOrInitStats(buyer);
    buyerStats.bought += 1;
    buyerStats.spent += price;
    saveUser(buyer);

    // update seller if exists
    if (seller && !seller.banned) {
      seller.points = (seller.points ?? 0) + price;
      const sStats = getOrInitStats(seller);
      sStats.sold += 1;
      sStats.earned += price;
      updateBadgesForUser(seller);
    }

    updateBadgesForUser(buyer);

    // update item
    item.status = "sold";
    item.buyer = buyer.username;
    items[idx] = item;
    saveArray(DB_KEYS.ITEMS, items);

    showToast("Purchase successful", "success");
    refreshNav();
    renderMarket();
    renderLeaderboards();
    renderAdminTable();
  }

  // ---------- chat ----------
  function renderChat() {
    const messages = loadArray(DB_KEYS.CHAT).sort(
      (a, b) => new Date(a.createdAt) - new Date(b.createdAt)
    );
    if (!messages.length) {
      chatMessages.innerHTML =
        '<p class="caption">No messages yet. Say hi!</p>';
      return;
    }
    chatMessages.innerHTML = "";
    messages.forEach(msg => {
      const div = document.createElement("div");
      let extraClass = "";
      if (msg.role === "management") extraClass += " chat-from-mgmt";
      if (currentSession.username && msg.sender === currentSession.username)
        extraClass += " chat-self";
      div.className = "chat-message" + extraClass;
      const timeStr = new Date(msg.createdAt).toLocaleTimeString([], {
        hour: "2-digit",
        minute: "2-digit"
      });
      div.innerHTML = `
        <div class="chat-meta-row">
          <span>${msg.sender}${
        msg.role === "management" ? " (Mgmt)" : ""
      }</span>
          <span>${timeStr}</span>
        </div>
        <div>${msg.text}</div>
      `;
      chatMessages.appendChild(div);
    });
    chatMessages.parentElement.scrollTop =
      chatMessages.parentElement.scrollHeight;
  }

  function sendChat() {
    if (!currentSession.username) {
      showToast("Log in to chat", "error");
      return;
    }
    const text = chatInput.value.trim();
    if (!text) return;
    const messages = loadArray(DB_KEYS.CHAT);
    messages.push({
      id: Date.now(),
      sender: currentSession.username,
      role: currentSession.role,
      text,
      createdAt: new Date().toISOString()
    });
    saveArray(DB_KEYS.CHAT, messages);
    chatInput.value = "";
    renderChat();
  }

  btnChatSend.addEventListener("click", sendChat);
  chatInput.addEventListener("keydown", e => {
    if (e.key === "Enter") {
      e.preventDefault();
      sendChat();
    }
  });

  // ---------- DMs ----------
  function getAllUsersForDm() {
    const users = loadArray(DB_KEYS.USERS);
    if (currentSession.role === "management") {
      // Mgmt can DM all civilians
      return users.filter(u => u.role === "civilian" && !u.banned);
    } else if (currentSession.role === "civilian") {
      // Civilian can DM all other civilians + management
      const list = users.filter(
        u => u.role === "civilian" && u.username !== currentSession.username
      );
      list.push({
        username: MGMT_USERNAME,
        role: "management",
        isVirtualMgmt: true
      });
      return list;
    }
    return [];
  }

  function rebuildDmUserList() {
    dmUserList.innerHTML = "";
    if (!currentSession.username) {
      dmUserList.innerHTML =
        '<div style="padding:8px;font-size:0.8rem;">Log in to use DMs.</div>';
      return;
    }
    const users = getAllUsersForDm();
    if (!users.length) {
      dmUserList.innerHTML =
        '<div style="padding:8px;font-size:0.8rem;">No other users yet.</div>';
      return;
    }

    users.forEach(u => {
      const div = document.createElement("div");
      div.className = "dm-user" + (currentDmTarget === u.username ? " active" : "");
      div.dataset.username = u.username;
      div.innerHTML = `
        <span>${u.username}</span>
        <span class="badge-role">${
          u.role === "management" ? "Mgmt" : "Civ"
        }</span>
      `;
      div.addEventListener("click", () => {
        currentDmTarget = u.username;
        rebuildDmUserList();
        renderDmMessages();
      });
      dmUserList.appendChild(div);
    });

    if (!currentDmTarget && users.length) {
      currentDmTarget = users[0].username;
      rebuildDmUserList();
    }
  }

  function renderDmMessages() {
    dmMessages.innerHTML = "";
    if (!currentSession.username || !currentDmTarget) {
      dmMessages.innerHTML =
        '<p class="caption">Select a user from the left to start chatting.</p>';
      return;
    }
    const all = loadArray(DB_KEYS.DMS).sort(
      (a, b) => new Date(a.createdAt) - new Date(b.createdAt)
    );
    const convo = all.filter(
      m =>
        (m.from === currentSession.username && m.to === currentDmTarget) ||
        (m.from === currentDmTarget && m.to === currentSession.username)
    );
    if (!convo.length) {
      dmMessages.innerHTML =
        '<p class="caption">No messages yet. Say hello!</p>';
      return;
    }
    convo.forEach(msg => {
      const div = document.createElement("div");
      let extra = "";
      if (msg.from === currentSession.username) extra = " chat-self";
      if (msg.fromRole === "management") extra += " chat-from-mgmt";
      div.className = "chat-message" + extra;
      const t = new Date(msg.createdAt).toLocaleTimeString([], {
        hour: "2-digit",
        minute: "2-digit"
      });
      div.innerHTML = `
        <div class="chat-meta-row">
          <span>${msg.from}${
        msg.fromRole === "management" ? " (Mgmt)" : ""
      }</span>
          <span>${t}</span>
        </div>
        <div>${msg.text}</div>
      `;
      dmMessages.appendChild(div);
    });
    dmMessages.parentElement.scrollTop =
      dmMessages.parentElement.scrollHeight;
  }

  function sendDm() {
    if (!currentSession.username || !currentDmTarget) {
      showToast("Select a user first", "error");
      return;
    }
    const text = dmInput.value.trim();
    if (!text) return;
    const dms = loadArray(DB_KEYS.DMS);
    dms.push({
      id: Date.now(),
      from: currentSession.username,
      to: currentDmTarget,
      fromRole: currentSession.role,
      toRole:
        currentDmTarget === MGMT_USERNAME ? "management" : "civilian",
      text,
      createdAt: new Date().toISOString()
    });
    saveArray(DB_KEYS.DMS, dms);
    dmInput.value = "";
    renderDmMessages();
  }

  btnDmSend.addEventListener("click", sendDm);
  dmInput.addEventListener("keydown", e => {
    if (e.key === "Enter") {
      e.preventDefault();
      sendDm();
    }
  });

  // ---------- leaderboards ----------
  function renderLeaderboards() {
    const users = loadArray(DB_KEYS.USERS).filter(
      u => u.role === "civilian" && !u.banned
    );
    users.forEach(u => {
      ensureBadgesArray(u);
      getOrInitStats(u);
    });

    // by points
    const byPoints = [...users].sort(
      (a, b) => (b.points ?? 0) - (a.points ?? 0)
    );
    lbPointsTableBody.innerHTML = "";
    byPoints.slice(0, 10).forEach((u, idx) => {
      const tr = document.createElement("tr");
      const badgesHtml = (u.badges || [])
        .map(b => `<span class="badge-pill badge-pill-gold">${b}</span>`)
        .join("");
      tr.innerHTML = `
        <td>${idx + 1}</td>
        <td>${u.username}</td>
        <td>${u.points ?? 0}</td>
        <td>${badgesHtml || "-"}</td>
      `;
      lbPointsTableBody.appendChild(tr);
    });

    // by sellers
    const bySold = [...users].sort(
      (a, b) => (b.stats?.sold ?? 0) - (a.stats?.sold ?? 0)
    );
    lbSellersTableBody.innerHTML = "";
    bySold.slice(0, 10).forEach((u, idx) => {
      const tr = document.createElement("tr");
      const badgesHtml = (u.badges || [])
        .map(b => `<span class="badge-pill badge-pill-blue">${b}</span>`)
        .join("");
      tr.innerHTML = `
        <td>${idx + 1}</td>
        <td>${u.username}</td>
        <td>${u.stats?.sold ?? 0}</td>
        <td>${badgesHtml || "-"}</td>
      `;
      lbSellersTableBody.appendChild(tr);
    });
  }

  // ---------- admin ----------
  function renderAdminTable() {
    if (currentSession.role !== "management") {
      adminUsersTableBody.innerHTML =
        '<tr><td colspan="7" style="font-size:0.8rem;color:#6b7280;">Management only.</td></tr>';
      return;
    }
    const users = loadArray(DB_KEYS.USERS).filter(u => u.role === "civilian");
    if (!users.length) {
      adminUsersTableBody.innerHTML =
        '<tr><td colspan="7" style="font-size:0.8rem;color:#6b7280;">No civilians yet.</td></tr>';
      return;
    }
    adminUsersTableBody.innerHTML = "";
    users.forEach(user => {
      ensureBadgesArray(user);
      const stats = getOrInitStats(user);
      const tr = document.createElement("tr");

      const tdUser = document.createElement("td");
      tdUser.textContent = user.username;

      const tdStatus = document.createElement("td");
      tdStatus.textContent = user.banned ? "Banned" : "Active";
      tdStatus.style.color = user.banned ? "#b91c1c" : "#166534";

      const tdPoints = document.createElement("td");
      tdPoints.textContent = user.points ?? 0;

      const tdSold = document.createElement("td");
      tdSold.textContent = stats.sold ?? 0;

      const tdBought = document.createElement("td");
      tdBought.textContent = stats.bought ?? 0;

      const tdBadges = document.createElement("td");
      tdBadges.innerHTML =
        (user.badges || [])
          .map(b => `<span class="badge-pill badge-pill-green">${b}</span>`)
          .join("") || "-";

      const tdActions = document.createElement("td");
      const banBtn = document.createElement("button");
      banBtn.className = "secondary small danger";
      banBtn.textContent = user.banned ? "Unban" : "Ban";
      banBtn.addEventListener("click", () => {
        user.banned = !user.banned;
        saveUser(user);
        showToast(
          user.banned
            ? `Banned ${user.username}`
            : `Unbanned ${user.username}`,
          "success"
        );
        renderAdminTable();
      });

      const ptsInput = document.createElement("input");
      ptsInput.type = "number";
      ptsInput.value = user.points ?? 0;
      ptsInput.style.width = "70px";
      ptsInput.style.marginLeft = "4px";
      ptsInput.style.fontSize = "0.75rem";

      const savePtsBtn = document.createElement("button");
      savePtsBtn.className = "secondary small";
      savePtsBtn.textContent = "Save";
      savePtsBtn.style.marginLeft = "4px";
      savePtsBtn.addEventListener("click", () => {
        const val = Number(ptsInput.value);
        if (isNaN(val) || val < 0) {
          showToast("Invalid points value", "error");
          return;
        }
        user.points = val;
        saveUser(user);
        updateBadgesForUser(user);
        showToast("Points updated for " + user.username, "success");
        renderAdminTable();
        if (
          currentSession.role === "civilian" &&
          currentSession.username === user.username
        ) {
          refreshNav();
        }
      });

      tdActions.appendChild(banBtn);
      tdActions.appendChild(ptsInput);
      tdActions.appendChild(savePtsBtn);

      tr.appendChild(tdUser);
      tr.appendChild(tdStatus);
      tr.appendChild(tdPoints);
      tr.appendChild(tdSold);
      tr.appendChild(tdBought);
      tr.appendChild(tdBadges);
      tr.appendChild(tdActions);

      adminUsersTableBody.appendChild(tr);
    });
  }

  // ---------- init ----------
  (function init() {
    refreshNav();
    refreshMainAccess();
    renderNotices();
    renderMarket();
    renderChat();
    renderLeaderboards();
  })();
</script>
</body>
</html>
