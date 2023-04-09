nmap-top-1000-ports
Bu repo, Nmap aracının default olarak kullandığı 1000 port numarası çıktısını içerir. Komut satırı üzerinden elde edilen çıktı nmap-top-1000-ports.txt dosyasında yer almaktadır.

Nasıl kullanılır?
Bu repo'yu klonladıktan sonra aşağıdaki komutu kullanarak nmap-top-1000-ports.txt dosyasını görüntüleyebilirsiniz:

cat nmap-top-1000-ports.txt
Nasıl oluşturuldu?
nmap-top-1000-ports.txt dosyası aşağıdaki komut kullanılarak elde edilmiştir:

bash
Copy code
grep -v '^#' /usr/share/nmap/nmap-services | grep '/tcp' | sort -rk3 | awk '{print $2}' | cut -d/ -f1 | head -n 1000 > nmap-top-1000-ports.txt
Komut, /usr/share/nmap/nmap-services dosyasındaki tüm TCP portlarına sahip servisleri listeleyerek, bu servislerin frekansına göre sıralar ve en popüler 1000'ini nmap-top-1000-ports.txt dosyasına yazar.
