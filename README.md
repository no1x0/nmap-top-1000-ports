# Nmap Top 1000 Ports

Bu repo, Nmap aracının varsayılan olarak kullandığı 1000 port numarasını içerir.

## Çıktı için kullanılan Linux komutu

```bash
grep -v '^#' /usr/share/nmap/nmap-services | grep '/tcp' | sort -rk3 | awk '{print $2}' | cut -d/ -f1 | head -n 1000 > nmap-top-1000-ports.txt
