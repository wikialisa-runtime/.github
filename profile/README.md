Lộ trình chuyển dịch của **Axioledger** từ giai đoạn **Testnet** (tập trung kiểm thử đa chuỗi trên **Bitcoin, Ethereum, Solana, Optimism**) sang vận hành chính thức trên **Mainnet** được chia làm 4 giai đoạn cốt lõi.

Mục tiêu xuyên suốt là đảm bảo mọi giao dịch đa chuỗi (Multi-chain) đều đạt chuẩn bảo mật phần cứng (Secure Element) và tương thích hoàn toàn với điện tín tài chính toàn cầu **SWIFT (ISO 20022)** trước khi mở rộng ra quy mô thực tế.

---

### Giai đoạn 1: Khởi tạo Hạ tầng Đa chuỗi (Multi-Chain Testnet Foundation)

Tập trung đồng bộ hóa chữ ký phần cứng (Clear Signing) và luồng dữ liệu cơ bản cho 4 mạng lưới mục tiêu trên môi trường thử nghiệm:

* **Bitcoin (BTC Testnet / Signet):** Kiểm thử cơ chế quản lý UTXO bên trong chip bảo mật, hỗ trợ chữ ký đa chữ ký (Multi-sig Taproot) cho các kho lưu trữ ngân quỹ doanh nghiệp.
* **Ethereum (ETH Sepolia / Holesky):** Thử nghiệm các Smart Contract định tuyến tài sản (Vaults), kiểm thử tiêu chuẩn ký minh bạch (EIP-712 Clear Signing) để loại bỏ rủi ro ký mù.
* **Solana (SOL Devnet / Testnet):** Tối ưu hóa tốc độ ký giao dịch tần suất cao (Ed25519) trên phần cứng, phục vụ các luồng thanh toán vi mô và quyết toán tức thời.
* **Optimism (OP Sepolia):** Kiểm thử giao dịch Layer 2 với chi phí gas tối thiểu, làm cầu nối trung chuyển thanh khoản giữa hệ sinh thái EVM và lớp điện tín tài chính.

---

### Giai đoạn 2: Tích hợp SWIFT ISO 20022 & Kiểm thử Chuyển mạch (Hybrid Sandbox)

Kết nối 4 mạng lưới Testnet ở Giai đoạn 1 với bộ định tuyến điện tín tài chính giả lập (Mock SWIFT Network):

* **Ánh xạ dữ liệu (Payload Mapping):** Chuyển đổi các bản tin chuẩn ngân hàng (như `pacs.008` cho chuyển tiền liên ngân hàng, `camt.053` cho sao kê) thành các lệnh gọi hàm (Calldata) trên ETH/OP/SOL hoặc giao dịch PSBT trên BTC.
* **Xác thực Định danh & Tuân thủ (eKYC / AML Gate):** Chạy thử nghiệm các node kiểm duyệt giao dịch để đảm bảo mọi ví tham gia luồng SWIFT Testnet đều gắn với mã định danh tổ chức (BIC/LEI) hợp lệ.
* **Mô phỏng Đối soát Thanh khoản (Atomic Settlement):** Thử nghiệm kịch bản chuyển đổi tự động giữa tiền pháp định (qua tin nhắn SWIFT) và tài sản số trên 4 mạng lưới mà không cần trung gian lưu ký.

---

### Giai đoạn 3: Kiểm toán Bảo mật & Diễn tập Tấn công (Security Audit & Stress Test)

Giai đoạn chốt chặn kỹ thuật bắt buộc trước khi chạm tới tài sản thật trên Mainnet:

* **Kiểm toán Phần cứng & Firmware:** Kiểm tra khả năng chống trích xuất khóa (Side-channel attacks) của lớp Secure Element khi xử lý đồng thời nhiều thuật toán mã hóa khác nhau (secp256k1 cho BTC/ETH/OP và Ed25519 cho SOL).
* **Kiểm toán Smart Contract & Cầu nối:** Rà soát toàn bộ mã nguồn hợp đồng trên ETH, OP, SOL thông qua các đơn vị kiểm toán độc lập và mở chương trình **Bug Bounty** công khai.
* **Kiểm thử chịu tải (Stress Test):** Bơm hàng triệu giao dịch giả lập liên tục qua bộ định tuyến ISO 20022 để đảm bảo không xảy ra nghẽn cổ chai hoặc lệch sổ cái giữa các chuỗi.

---

### Giai đoạn 4: Chuyển đổi Chính thức sang Mainnet (Mainnet Genesis & Rollout)

Triển khai theo chiến lược mở rộng có kiểm soát (Phased Rollout) để bảo vệ an toàn tuyệt đối cho dòng tiền:

1. **Mainnet Guarded Launch (Giai đoạn Giới hạn):**
* Kích hoạt mạng chính cho BTC, ETH, SOL, OP với hạn mức giá trị giao dịch (TVL Cap) được kiểm soát.
* Chỉ mở quyền kết nối điện tín SWIFT cho các đối tác doanh nghiệp, ngân hàng và tổ chức nằm trong danh sách trắng (Whitelisted Nodes).


2. **Mở rộng Hệ sinh thái & SDK Công khai:**
* Phát hành chính thức bộ **Axio Core CLI**, **Device Management SDK** và **ISO 20022 Parser** bản Production cho cộng đồng lập trình viên tự do tích hợp.
* Gỡ bỏ giới hạn hạn mức giao dịch sau 90 ngày vận hành ổn định không sự cố.


3. **Liên thông Chính phủ & Định chế Tài chính:**
* Mở rộng cổng kết nối sang các hệ thống thanh toán công, hỗ trợ thanh toán xuyên biên giới quy mô lớn và vận hành quỹ dự trữ tài sản số đa chuỗi chuẩn quốc tế.



---

### Bảng tóm tắt Tiến trình Chuyển đổi

| Giai đoạn | Môi trường | Trọng tâm Kỹ thuật | Tiêu chí Hoàn thành (Milestone) |
| --- | --- | --- | --- |
| **1. Multi-chain Core** | BTC, ETH, SOL, OP Testnet | Clear Signing đa thuật toán (secp256k1 & Ed25519) | Ký và phát giao dịch thành công trên cả 4 chuỗi từ phần cứng |
| **2. SWIFT Bridge** | Hybrid Sandbox | Bộ chuyển đổi ISO 20022 & Bộ lọc eKYC/AML | Đối soát thành công bản tin ngân hàng với giao dịch on-chain |
| **3. Hardening** | Pre-Mainnet / Staging | Kiểm toán bảo mật (Audit) & Bug Bounty | Đạt 100% tiêu chuẩn an toàn phần cứng & Smart Contract |
| **4. Mainnet** | Production Network | Guarded Launch -> Mở rộng toàn cầu | Vận hành ổn định dòng tiền thực tế cho Doanh nghiệp & Tổ chức |
