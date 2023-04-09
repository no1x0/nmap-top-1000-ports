# Nmap Top 1000 TCP Ports - 2023

2023 yılında oluşturulan bu repo, `nmap-top-1000-ports.txt` adlı bir dosya içermektedir. Bu dosya, Nmap'in öntanımlı hizmetlerinden en popüler 1000 TCP portunu listelemektedir. Aşağıdaki Linux terminal komutu ile oluşturulmuştur:

```bash
grep -v '^#' /usr/share/nmap/nmap-services | grep '/tcp' | sort -rk3 | awk '{print $2}' | cut -d/ -f1 | head -n 1000 > nmap-top-1000-ports.txt
```


## Komut Açıklaması

1. `grep -v '^#' /usr/share/nmap/nmap-services`: Nmap hizmetlerini içeren dosyadan yorum satırlarını (`#` ile başlayan satırlar) hariç tutarak okur.
2. `grep '/tcp'`: Sadece TCP ile ilgili satırları filtreler.
3. `sort -rk3`: Üçüncü sütundaki değerlere göre satırları ters sıralar (en yüksekten en düşüğe).
4. `awk '{print $2}'`: İkinci sütundaki değerleri yazdırır (port adı ve protokolü).
5. `cut -d/ -f1`: Port numarasını ve protokolü ayırarak sadece port numarasını alır.
6. `head -n 1000`: İlk 1000 satırı alır.
7. `> nmap-top-1000-ports.txt`: Çıktıyı `nmap-top-1000-ports.txt` dosyasına yönlendirir.

## Kullanım

Bu repo, güvenlik testleri ve ağ taramalarında kullanılabilir. Nmap ile birlikte kullanarak, en popüler 1000 TCP portunu hedef alarak tarama yapabilirsiniz.

## Lisans

Bu repo, herkesin kullanımına açıktır ve istediğiniz gibi değiştirilebilir, dağıtılabilir ve kullanılabilir.
