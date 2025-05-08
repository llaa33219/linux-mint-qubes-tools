## 🛠 Qubes Tools 설치 (Linux Mint qube에서)

Qubes OS 안의 리눅스 민트 qube에 `qubes-core-agent`를 설치해서 클립보드 공유, 창 모드 등 기능을 활성화하는 절차입니다.

---

### 1️⃣ GPG 키 가져오기

\`\`\`bash
curl -fsSL https://keys.qubes-os.org/keys/qubes-release-4-signing-key.asc \
| gpg --dearmor \
| sudo tee /usr/share/keyrings/qubes-archive-keyring.gpg > /dev/null
\`\`\`

---

### 2️⃣ Qubes 패키지 저장소 추가

\`\`\`bash
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/qubes-archive-keyring.gpg] \
http://deb.qubes-os.org/r4.1/vm bullseye main" \
| sudo tee /etc/apt/sources.list.d/qubes-vm.list
\`\`\`

---

### 3️⃣ 패키지 목록 업데이트

\`\`\`bash
sudo apt update
\`\`\`

---

### 4️⃣ Qubes Tools 설치

\`\`\`bash
sudo apt install qubes-core-agent
\`\`\`

> ⚠️ 추가 기능 원할 시:
> \`\`\`bash
> sudo apt install qubes-core-agent-qrexec qubes-core-agent-networking qubes-gui-agent
> \`\`\`

---

### 5️⃣ 재부팅

\`\`\`bash
sudo reboot
\`\`\`

---

설치 후 Qubes Manager에서 해당 qube가 창 모드로 뜨고, 클립보드 공유가 동작하면 성공입니다.
문제 발생 시 알려주세요.
