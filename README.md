# Visualisasi Informasi menggunakan chart.js


## General Info
Halo! Saya Reyhan Venyutzky nrp 05211840000031. Project ini merupakan tugas UTS kelas Visualisasi Informasi ITS. Inti dari project ini berhasil membuat visualisasi dari data menggunakan chart.js

### Dataset
Dataset yang digunakan adalah data berisi kecelakaan pesawat dan dataset berasal dari website kaggle dengan link berikut <br>
https://www.kaggle.com/datasets/deepcontractor/aircraft-accidents-failures-hijacks-dataset
<br>

### Tahapan Pembagunan Visualisasi Data

#### Persiapan Dataset
Dari dataset tersebut dilakukan processing untuk memilih data yang ingin ditampilkan. Berikut merupakan data yang ingin divisualisasikan yaitu.<br>
![image](https://user-images.githubusercontent.com/54930670/162118955-b7dbf6b6-fb69-49ba-93d6-33e32f02cc3f.png)
<br>

####1. Melakukan Konfigurasi Data <br>
langkah pertama yaitu membuat const data yang berisikan dataset yang digunakan.<br>
```
 const data = {
            labels: ['2011', '2012','2013','2014','2015','2016','2017','2018','2019','2020','2021'],
            datasets: [{
                type: 'line',
                label: 'Total Kecelakaan',
                data: [187,169,208,225,220,205,192,224,237,180,148,],
                borderColor: 'rgb(255, 99, 132)',
                backgroundColor: 'rgba(255, 99, 132)'
            }, {
                type: 'bar',
                label: 'Total Korban Jiwa',
                data: [713,689,355,1219,840,567,317,963,471,430,330,],
                fill: 50,
                borderColor: 'rgb(153, 204, 255)',
                backgroundColor: 'rgb(153, 204, 255)'
            }]
        };
```

