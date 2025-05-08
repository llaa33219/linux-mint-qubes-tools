리눅스 민트 qube에서 Qubes Tools를 설치하려면 다음 단계를 따르세요:

Qubes GPG 키 가져오기:

bash
복사
편집
curl -fsSL https://keys.qubes-os.org/keys/qubes-release-4-signing-key.asc | gpg --dearmor | sudo tee /usr/share/keyrings/qubes-archive-keyring.gpg > /dev/null
Qubes OS Repository 추가:

bash
복사
편집
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/qubes-archive-keyring.gpg] http://deb.qubes-os.org/r4.1/vm bullseye main" | sudo tee /etc/apt/sources.list.d/qubes-vm.list
패키지 목록 업데이트:

bash
복사
편집
sudo apt update
Qubes Tools 설치:

bash
복사
편집
sudo apt install qubes-core-agent
시스템 재부팅:

bash
복사
편집
sudo reboot
이후에는 Qubes OS의 Qube Manager에서 해당 qube의 창이 윈도우 모드로 뜨거나, 클립보드 공유, 파일 복사 등이 가능해질 것입니다. 일부 기능은 수동으로 활성화해야 할 수도 있습니다.

설치 중 에러나 실패 메시지가 뜨면 알려주세요. 패키지 충돌이나 서비스 실패가 날 수 있어요.


출처
