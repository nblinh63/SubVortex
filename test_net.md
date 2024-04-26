# CÁCH CHẠY TRÊN TESTNET
### B1. Request TAO trên testnet.
Cách 1. Request từ bittensor tại mục help trên discord.
https://discord.com/channels/799672011265015819/1190048018184011867
<br>
Nội dung:
```sh
Requesting Testnet TAO 
Reason: Testing my custom miner
Testnet UID: 25
Mainnet UID: 26
Roles: Miner
Coldkey: 5F4TnCKakAtUQkdh7A9eJeMe7MpVbtWexJGkYhFt7N6V9uRD
Thank you
```
*Xem uid của testnet tương ứng với mỗi subnet ở đây:*
https://discord.com/channels/799672011265015819/1182445225801691226/1182445225801691226
<br>
<br>
*Chuyển TAO trên testnet*
```sh
btcli w transfer --subtensor.network test
```
<br>
Cách 2. Gửi tin nhắn cho admin của các subnet trên discord để xin.
<br>
Nội dung:

```sh
hello, could you please send me a few tao to my test net wallet, then I can test my custom miner on testnet. thank you!
my coldkey: 5F4TnCKakAtUQkdh7A9eJeMe7MpVbtWexJGkYhFt7N6V9uRD
```

### B2. Kiểm tra xem có TAO trên wallet của testnet chưa & Đăng ký trên testnet.
1. Kiểm tra wallet trên testnet
```sh
btcli w balance
Enter wallet path >> gõ enter
Enter wallet name >> điền coldkey name
Enter network >> điền test
```

2. Đăng ký trên testnet
```sh
btcli subnet register --wallet.name dungck1 --wallet.hotkey dunghk1 --subtensor.network test --netuid 29
```

### B3. Chạy miner trên testnet.
Cách set up giống như chạy trên mainnet, chỉ khác lệnh start. thay vì **--subtensor.network finney**, chuyển thành **--subtensor.network test**
