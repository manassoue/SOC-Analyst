# Commands used (Week 03)

## TShark
- Capture on interface:
  - `tshark -i <iface> -w capture.pcap`
- Quick summary:
  - `tshark -r capture.pcap -q -z conv,tcp`
- Filter examples:
  - `tshark -r capture.pcap -Y "dns" -T fields -e frame.time -e ip.src -e dns.qry.name`

## Zeek
- Run Zeek on interface or pcap:
  - `zeek -i <iface>`
  - `zeek -r capture.pcap`
- Useful logs:
  - `conn.log`, `dns.log`, `http.log`

## Suricata
- Update rules (example):
  - `<your rule update command/process>`
- Run and check alerts:
  - `fast.log` or `eve.json`
