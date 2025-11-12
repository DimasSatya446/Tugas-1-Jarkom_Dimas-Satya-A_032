# Tugas-1-Jarkom_Dimas-Satya-A_032
# Topologi
<img width="1748" height="1180" alt="image" src="https://github.com/user-attachments/assets/33b2449c-7809-49e7-96d3-054ddf688f0b" />

# Base Network
NRP: `5027241032` <mod 256> = 72

Base Network: 10.72.0.0

| Subnet | Host | Prefix |
| :-------- | :------- | :------- |
| Sekretariat | 381 | /23 |  
| Kurikulum | 221 | /24 |
| Bidang guru & tendik | 96 | /25 |
| Bidang sarana & prasarana | 46 | /26 |    
| Bidang pengawas sekolah | 19 | /27 |  
| Server & admin | 7 | /29 |  
| Router interlink | 6 | /29 |  
| P2P branch | 2 | /30 | 
| **Total** | **778** | **/22** |


# VLSM
<img width="1842" height="1202" alt="image" src="https://github.com/user-attachments/assets/0ff92912-27fc-4444-b57d-1784566c369d" />

| Subnet                                      | Host pada Subnet | Network     | Mask            | Prefix | Range Host                | Broadcast   | Gateway     |
| ------------------------------------------- | ---------------: | ----------- | --------------- | ------ | ------------------------- | ----------- | ----------- |
| Sekretariat                                 |          **381** | 10.72.0.0   | 255.255.254.0   | /23    | 10.72.0.1 – 10.72.1.254   | 10.72.1.255 | 10.72.0.1   |
| Bidang Kurikulum                            |          **221** | 10.72.2.0   | 255.255.255.0   | /24    | 10.72.2.1 – 10.72.2.254   | 10.72.2.255 | 10.72.2.1   |
| Bidang Guru & Tendik                        |           **96** | 10.72.3.0   | 255.255.255.128 | /25    | 10.72.3.1 – 10.72.3.126   | 10.72.3.127 | 10.72.3.1   |
| Bidang Sarana Prasarana                     |           **46** | 10.72.3.128 | 255.255.255.192 | /26    | 10.72.3.129 – 10.72.3.190 | 10.72.3.191 | 10.72.3.129 |
| Bidang Pengawas Sekolah (Cabang)            |           **19** | 10.72.3.192 | 255.255.255.224 | /27    | 10.72.3.193 – 10.72.3.222 | 10.72.3.223 | 10.72.3.193 |
| Server & Admin                              |            **7** | 10.72.3.224 | 255.255.255.248 | /29    | 10.72.3.225 – 10.72.3.230 | 10.72.3.231 | 10.72.3.225 |
| **Router Interlink** (router ↔ switch inti) |            **6** | 10.72.3.232 | 255.255.255.248 | /29    | 10.72.3.233 – 10.72.3.238 | 10.72.3.239 | 10.72.3.233 |
| **P2P** (Router HQ ↔ Router Branch)         |            **2** | 10.72.3.240 | 255.255.255.252 | /30    | 10.72.3.241 – 10.72.3.242 | 10.72.3.243 | 10.72.3.241 |

# CIDR
| Network         | Mask            | Prefix  | Range Host                | Broadcast   | Gateway     | Keterangan (Agregasi dari Subnet VLSM)                                                                                                                    |
| --------------- | --------------- | ------- | ------------------------- | ----------- | ----------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **10.72.0.0**   | 255.255.252.0   | **/22** | 10.72.0.1 – 10.72.3.254   | 10.72.3.255 | 10.72.0.1   | **Supernet Kantor Pusat** → gabungan: Sekretariat (/23), Kurikulum (/24), Guru & Tendik (/25), Sarpras (/26), Pengawas (Cabang /27), Server & Admin (/29) |
| **10.72.3.232** | 255.255.255.248 | **/29** | 10.72.3.233 – 10.72.3.238 | 10.72.3.239 | 10.72.3.233 | **Subnet Router Interlink** (penghubung Router Core ↔ Switch utama kantor pusat)                                                                          |
| **10.72.3.240** | 255.255.255.252 | **/30** | 10.72.3.241 – 10.72.3.242 | 10.72.3.243 | 10.72.3.241 | **Link P2P (Router HQ ↔ Router Cabang)**                                                                                                                  |
