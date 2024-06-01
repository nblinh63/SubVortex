# Chạy subnet Mosaic - uid 14

1. Cài đặt chung

```sh
sudo apt update
sudo apt install nano -y
sudo apt install python3-pip -y
apt install npm -y
npm i -g pm2 -y
sudo apt install python3.10-venv -y
sudo apt install vim -y
pip install communex
```

2. Tạo ví và đăng ký
- Mỗi một ví chỉ đăng ký được 1 subnet
- key-name điền tên ví, ví dụ: dungnd
```shell
comx key create <key-name>
```
- Xem lại thông tin ví (nhớ lưu lại mnemonic)
```shell
comx key show dungnd --show-private
```
- Sau khi tạo xong thì đăng ký vào subnet
```shell
comx module register <module-name> <key-name> --netuid=14 --ip=<your-public-ip> --port=<port>
```
trong đó module name: Tên hiển thị trên subnet (là gì cũng được)
key-name: Tên ví vừa tạo
your-public-ip: ip của máy thuê trên vast
port: cổng của máy thuê trên vast

3. Hướng dẫn cài poetry:

```shell
curl -sSL https://install.python-poetry.org | python3 -
echo 'export PATH="/root/.local/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

4. Kéo project về

```sh
git clone https://github.com/mosaicx-org/mosaic-subnet
cd mosaic-subnet
poetry shell
poetry install
pm2 start mosaic_subnet/cli.py --interpreter python3 -n <pm2-name> -- miner <key-name> 0.0.0.0 <port>
```
- Lưu ý chạy từng lệnh
- pm2-name: là gì cũng đc
- key-name: ví vừa đăng ký subnet
- port: cổng trên vast vừa dùng đăng ký subnet

5. Xem thông tin điểm và reward
https://leaderboard.mosaicx.org/