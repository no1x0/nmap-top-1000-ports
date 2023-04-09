# nmap-top-1000-ports
Nmap aracının default olarak kullandığı 1000 port numarası



# Çıktı için kullanılan linux komut satırı

'''
grep -v '^#' /usr/share/nmap/nmap-services | grep '/tcp' | sort -rk3 | awk '{print $2}' | cut -d/ -f1 | head -n 1000 > nmap-top-1000-ports.txt
'''
