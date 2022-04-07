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

#### 1. Melakukan Konfigurasi Data <br>
langkah pertama yaitu membuat const data yang berisikan dataset yang digunakan.<br>
```
 const data = {
            labels: ['2011', '2012','2013','2014','2015','2016','2017','2018','2019','2020','2021'],
            datasets: [{
                type: 'bar',
                label: 'Total Kecelakaan',
                data: [187,169,208,225,220,205,192,224,237,180,148,],
                fill: 50,
                borderColor: 'rgb(153, 204, 255)',
                backgroundColor: 'rgb(153, 204, 255)',
                yAxisID: 'y'
            }, {
                type: 'line',
                label: 'Total Korban Jiwa',
                data: [713,689,355,1219,840,567,317,963,471,430,330,],
                borderColor: 'rgb(255, 99, 132)',
                backgroundColor: 'rgba(255, 99, 132)',
                yAxisID: 'y1'
            }]
        };
```
untuk data total kecelakaan diset `type : bar` dan untuk total korban jiwa diset `type: line`

#### 2. Melakukan Konfigurasi Charts <br>
```
const config = {
            data: data,
            options: {
            }
}
```
Langkah selanjutnya adalah membuat tampilan charts lebih interaktif <br>
##### Memberikan Title
Di dalam `options` tambahkan `plugins` array <br>
```
                 plugins: {
                    responsive: true,
                    // untuk title
                    title: {
                        display: true,
                        text: 'Kecelakaan Pesawat Selama Tahun 2011 -2021',
                        font: {
                            size: 25,
                            weight: 'bold'
                        },
                        padding: {
                            top: 10,
                            bottom: 30
                        }
                    },
```
##### Memberikan legend dengan posisi di atas chart
Di dalam `plugins` tambahkan code berikut <br>
```
legend: {
    display: true,
    position: 'top',
    }
},
```
#### Memberikan animasi delay chart tampil di awal
Di dalam `options` tambahkan `animation` array tapi sebelumnya menambakhan variable dengan nama `delayed` <br>
```
// variabel 
        let delayed;
        const config = {
            data: data,
```
Kemudian menambahkan kode berikut
```
onComplete: () => {
     delayed = true;
},
delay: (context) => {
     let delay = 0;
     if (context.type === 'data' && context.mode === 'default' && !delayed) {
           delay = context.dataIndex * 300 + context.datasetIndex * 100;
     }
      return delay;
}
```
#### Memberikan animasi Loop dan ubah warna ketika mouse dihover ke chart
```
animation: {
    // untuk animasi loop
    radius: {
         duration: 400,
         easing: 'linear',
         loop: (context) => context.active
    },
    hoverRadius: 10,
    hoverBackgroundColor: 'rgb(0, 128, 255)',
    interaction: {
          mode: 'nearest',
          intersect: false,
           axis: 'x'
     }
```


                    



