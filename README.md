Không user & pass:
             bash <(curl -s "https://raw.githubusercontent.com/fcsaurom/proxyv6/main/proxy.sh")

Có user & pass:
             bash <(curl -s "https://raw.githubusercontent.com/fcsaurom/proxyv6/main/setup.sh")

-----------------------------------------------------------------------------------

Multi Proxy trên CentOS 7.9

Chạy các dòng lệnh sau để có quyền ghi trên file ifcfg-eth0:

sudo touch /etc/sysconfig/network-scripts/ifcfg-eth0
sudo chown root:root /etc/sysconfig/network-scripts/ifcfg-eth0
sudo chmod 775 /etc/sysconfig/network-scripts/ifcfg-eth0
whoami

Sửa file ifcfg-eth0:

vi /etc/sysconfig/network-scripts/ifcfg-eth0

Chèn đoạn sau xuống dưới cùng:

IPV6_FAILURE_FATAL=no
IPV6_ADDR_GEN_MODE=stable-privacy
IPV6ADDR=2604:6280:105:5c:510::1/80
IPV6_DEFAULTGW=2604:6280:105:5c::1
 

Chèn đoạn mã trên xong nhấn phím Esc và gõ lệnh để lưu lại:

:w !chmod 777 %
:wq!

(Lưu ý IPV6 được nhà cung cấp VPS cấp khi mua)

IPV6: 2604:6280:105:5c:510::1
Nesmask: 80
Geteway: 2604:6280:105:5c::1
Hãy check email hoặc trong phần thông tin dịch vụ khi mua


Khởi động lại mạng bằng lệnh:

service network restart

Sau đó chạy dòng lệnh sau để cài 3proxy:

wget https://raw.githubusercontent.com/fcsaurom/proxyv6/main/setup.sh && chmod +x setup.sh && bash setup.sh
