# Coding Aplikasi Web Untuk Menghitung Saham

Aplikasi ini akan dipakai di **Virtual Private Server (VPS)** yang ada di internet. Data didapatkan dari sumber terbuka yang bisa diketemukan di situs **IDX**. Jadi data ini tidak akan menimbulkan kebocoran data. Untuk contoh pertama akan mengambil data dari laporan keuangan emiten berkode saham **ARNA**.  Untuk bahasa pemrograman salah satunya adalah menggunakan **PHP 7**. Untuk database akan menggunakan **MariaDB/MYSQL** . Untuk codingan menggunakan native dan nantinya bisa menggunakan framework, yaitu **codeigniter** .


## Coding Tampilan Form

```html

  <!DOCTYPE html>

<html>


    <head>

        <meta name="viewport" content="width=device-width, initial-scale=1">

        <style>

            * {

                box-sizing: border-box;
            }


            input[type=text], select, textarea{

                width: 100%;

                padding: 12px;

                border: 1px solid #ccc;

                border-radius: 4px;

                resize: vertical;

            }


            label{


                padding: 12px 12px 12px 0;

                display: inline-block;
            }


            input[type=submit]:hover {

                background-color: #45a049;

            }

            .container{

                border-radius: 5px;

                background-color: #f2f2f2;

                padding: 20px;

            }

            .col-25{

                float: left;

                width: 25%;

                margin-top: 6px;
            }


            .col-75{

                float: left;

                width: 75%;

                margin-top: 6px;


            }


            /* clear folats after the columns */

            .row::after {


                content: "";

                display: table;

                clear: both;


            }


            /* Responsive layout - when the screen is less than 600px wide, make the two columns stack on top of each other instead of next to each other */

            @media screen and (max-width: 600px){


                .col-25, .col-75, input[type=submit] {

                    width: 100%;

                    margin-top: 0;

                }
            }



        </style>



    </head>


    <body>

        <h2>Responsif Form</h2>

        <p>Resize the browser window to see the effect. When the screen is less than 600px wide, make the two columns stack on top of each other instead of next to each other.</p>

        <div class="container">

            <form action="/action_page.php">




                <div class="row">

                    <div class="col-25">

                        <label for="tanggal">Tanggal</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="tanggal" name="tanggal" placeholder="Tanggal Laporan Keuangan ..">

                    </div>


                </div>




                <div class="row">

                    <div class="col-25">

                        <label for="kassetara">Kas dan Setara Kas</label>

                    </div>
					
					
					<div class="col-75">

                        <input type="text" id="kassetara" name="kassetara" placeholder="Kas dan Setara Kas ...">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="piutangusahapihakketiga">Piutang Usaha Pihak Ketiga</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="piutangusahapihakketiga" name="piutangusahapihakketiga" placeholder="Piutang Usaha Pihak Ketiga ... ">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="piutangusahapihakberelasi">Piutang Usaha Pihak Berelasi</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="piutangusahapihakberelasi" name="piutangusahapihakberelasi" placeholder="Piutang Usaha Pihak Berelasi ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="piutanglainnyapihakketiga">Piutang Lainnya Pihak Ketiga</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="piutanglainnyapihakketiga" name="piutanglainnyapihakketiga" placeholder="Piutang Lainnya Pihak Ketiga ... ">

                    </div>

                </div>




                <div class="row">

                    <div class="col-25">

                        <label for="persediaanlancarlainnya">Persediaan Lancar Lainnya</label>

                    </div>

                    <div class="col-75">


                        <input type="text" id="persediaanlancarlainnya" name="persediaanlancarlainnya" placeholder="Persediaan Lancar Lainnya ...">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="biayadibayardimukalancar">Biaya Di Bayar Di Muka Lancar</label>

                    </div>


                    <div class="col-75">


                        <input type="text" id="biayadibayardimukalancar" name="biayadibayardimukalancar" placeholder="Biaya Di Bayar Di Muka Lancar ... ">

                    </div>


                </div>


                <div class="row">

                    <div class="col-25">

                        <label for="pajakdibayardimukalancar">Pajak Di Bayar Di Muka Lancar</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="pajakdibayardimukalancar" name="pajakdibayardimukalancar" placeholder="Pajak Di Bayar Di Muka Lancar ... ">


                    </div>


                </div>





                <div class="row">

                    <div class="col-25">

                        <label for="asetnonkeuanganlancarlainnya">Aset Non Keuangan Lancar Lainnya</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="asetnonkeuanganlancarlainnya" name="asetnonkeuanganlancarlainnya" placeholder="Aset Non Keuangan Lancar Lainnya ... ">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="jumlahasetlancar">Jumlah Aset Lancar</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="jumlahasetlancar" name="jumlahasetlancar" placeholder="Jumlah Aset Lancar ...">

                    </div>

                </div>



                <div class="row">


                    <div class="col-25">

                        <label for="asetpajaktangguhan">Aset Pajak Tangguhan</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="asetpajaktangguhan" name="asetpajaktangguhan" placeholder="Aset Pajak Tangguhan ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="asettetap">Aset Tetap</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="asettetap" name="asettetap" placeholder="Aset Tetap ... ">

                    </div>


                </div>


                <div class="row">

                    <div class="col-25">

                        <label for="asettidaklancarnonkeuanganlainnya">Aset Tidak Lancar Non-Keuangan Lainnya</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="asettidaklancarnonkeuanganlainnya" name="asettidaklancarnonkeuanganlainnya" placeholder="Aset Tidak Lancar Non-Keuangan Lainnya ... ">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="jumlahasettidaklancar">Jumlah Aset Tidak Lancar</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="jumlahasettidaklancar" name="jumlahasettidaklancar" placeholder="Jumlah Aset Tidak Lancar ... ">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="jumlahaset">Jumlah Aset</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="jumlahaset" name="jumlahaset" placeholder="Jumlah Aset ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="pinjamanjangkapendek">Pinjaman Jangka Pendek</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="pinjamanjangkapendek" name="pinjamanjangkapendek" placeholder="Pinjaman Jangka Pendek ... ">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="utangusahapihakketiga">Utang Usaha Pihak Ketiga</label>

                    </div>

                    
                    <div class="col-75">

                        <input type="text" id="utangusahapihakketiga" name="utangusahapihakketiga" placeholder="Utang Usaha Pihak Ketiga ... ">

                    </div>

                </div>





                <div class="row">

                    <div class="col-25">

                        <label for="utanglainnyapihakketiga">Utang Lainnya Pihak Ketiga</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="utanglainnyapihakketiga" name="utanglainnyapihakketiga" placeholder="Utang Lainnya Pihak Ketiga ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="utangdividen">Utang Dividen</label>
                        
                    </div>

                    <div class="col-75">

                        <input type="text" id="utangdividen" name="utangdividen" placeholder="Utang Dividen ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="liabilitaskeuanganjangkapendeklainnya">Liabilitas Keuangan Jangka Pendek Lainnya</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="liabilitaskeuanganjangkapendeklainnya" name="liabilitaskeuanganjangkapendeklainnya" placeholder="Liabilitas Keuangan Jangka Pendek Lainnya ... ">

                    </div>

                </div>





                <div class="row">

                    <div class="col-25">

                        <label for="bebanakrualjangkapendek">Beban Akrual Jangka Pendek</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="bebanakrualjangkapendek" name="bebanakrualjangkapendek" placeholder="Beban Akrual Jangka Pendek ... ">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="utangpajak">Utang Pajak</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="utangpajak" name="utangpajak" placeholder="Utang Pajak ... ">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="liabilitasjangkapanjangjatuhtempo1tahun">Liabilitas Jangka Panjang Jatuh Tempo 1 Tahun Atas Utang Bank</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="liabilitasjangkapanjangjatuhtempo1tahun" name="liabilitasjangkapanjangjatuhtempo1tahun" placeholder="Liabilitas Jangka Panjang Jatuh Tempo 1 Tahun Atas Utang Bank ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="jumlahliabilitasjangkapendek">Jumlah Liabilitas Jangka Pendek</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="jumlahliabilitasjangkapendek" name="jumlahliabilitasjangkapendek" placeholder="Jumlah Liabilitas Jangka Pendek ... ">


                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="liabilitasjangkapanjangatasutangbank">Liabilitas Jangka Panjang Atas Utang Bank</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="liabilitasjangkapanjangatasutangbank" name="liabilitasjangkapanjangatasutangbank" placeholder="Liabilitas Jangka Panjang Atas Utang Bank ... ">

                    </div>

                </div>




                <div class="row">

                    <div class="col-25">

                        <label for="kewajibanimbalanpascakerjajangkapanjang">Kewajiban Imbalan Pasca Kerja Jangka Panjang</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="kewajibanimbalanpascakerjajangkapanjang" name="kewajibanimbalanpascakerjajangkapanjang" placeholder="Kewajiban Imbalan Pasca Kerja Jangka Panjang ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="liabilitaskeuanganjangkapanjanglainnya">Liabilitas Keuangan Jangka Panjang Lainnya</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="liabilitaskeuanganjangkapanjanglainnya" name="liabilitaskeuanganjangkapanjanglainnya" placeholder="Liabilitas Keuangan Jangka Panjang Lainnya ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="jumlahliabilitasjangkapanjang">Jumlah Liabilitas Jangka Panjang</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="jumlahliabilitasjangkapanjang" name="jumlahliabilitasjangkapanjang" placeholder="Jumlah Liabilitas Jangka Panjang ... ">

                    </div>

                </div>


                <div class="row">

                    <div class="col-25">

                        <label for="jumlahliabilitas">Jumlah Liabilitas</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="jumlahliabilitas" name="jumlahliabilitas" placeholder="Jumlah Liabilitas ... ">

                    </div>

                </div>


                <div class="row">

                    <div class="col-25">

                        <label for="sahambiasa">Saham Biasa</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="sahambiasa" name="sahambiasa" placeholder="Saham Biasa ... ">

                    </div>

                </div>


                <div class="row">

                    <div class="col-25">

                        <label for="tambahanmodaldisetor">Tambahan Modal Di Setor</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="tambahanmodaldisetor" name="tambahanmodaldisetor" placeholder="Tambahan Modal Di Setor ... ">

                    </div>

                </div>


                <div class="row">

                    <div class="col-25">

                        <label for="saldolabayangbelumditentukanpenggunaannya">Saldo Laba Yang Belum Ditentukan Penggunaannya</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="saldolabayangbelumditentukanpenggunaannya" name="saldolabayangbelumditentukanpenggunaannya" placeholder="Saldo Laba Yang Belum Ditentukan Penggunaannya ... ">

                    </div>

                </div>





                <div class="row">

                    <div class="col-25">

                        <label for="jumlahekuitasyangdiatribusikankepadapemilik">Jumlah Ekuitas Yang Diatribusikan Kepada Pemilik</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="jumlahekuitasyangdiatribusikankepadapemilik" name="jumlahekuitasyangdiatribusikankepadapemilik" placeholder="Jumlah Ekuitas Yang Diatribusikan Kepada Pemilik ... ">

                    </div>

                </div>


                <div class="row">

                    <div class="col-25">

                        <label for="kepentingannonpengendali">Kepentingan Non Pengendali</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="kepentingannonpengendali" name="kepentingannonpengendali" placeholder="Kepentingan Non Pengendali ... ">

                    </div>


                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="jumlahekuitas">Jumlah Ekuitas</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="jumlahekuitas" name="jumlahekuitas" placeholder="Jumlah Ekuitas ... ">

                    </div>


                </div>




                <div class="row">

                    <div class="col-25">

                        <label for="jumlahliabilitasdanekuitas">Jumlah Liabilitas Dan Ekuitas</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="jumlahliabilitasdanekuitas" name="jumlahliabilitasdanekuitas" placeholder="Jumlah Liabilitas Dan Ekuitas ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="penjualandanpendapatanusaha">Penjualan Dan Pendapatan Usaha</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="penjualandanpendapatanusaha" name="penjualandanpendapatanusaha" placeholder="Penjualan Dan Pendapatan Usaha ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="bebanpokokpenjualandanpendapatan">Beban Pokok Penjualan Dan Pendapatan</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="bebanpokokpenjualandanpendapatan" name="bebanpokokpenjualandanpendapatan" placeholder="Beban Pokok Penjualan Dan Pendapatan ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="jumlahlababruto">Jumlah Laba Bruto</label>

                    </div>


                    <div class="col-75">

                        <input type="text" id="jumlahlababruto" name="jumlahlababruto" placeholder="Jumlah Laba Bruto ... ">


                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="bebanpenjualan">Beban Penjualan</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="bebanpenjualan" name="bebanpenjualan" placeholder="Beban Penjualan ... ">

                    </div>

                </div>



                <div class="row">

                    <div class="col-25">

                        <label for="bebanumumdanadministrasi">Beban Umum Dan Administrasi</label>

                    </div>

                    <div class="col-75">

                        <input type="text" id="bebanumumdanadministrasi" name="bebanumumdanadministrasi" placeholder="Beban Umum Dan Administrasi ... ">

                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="pendapatankeuangan">Pendapatan Keuangan</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="pendapatankeuangan" name="pendapatankeuangan" placeholder="Pendapatan Keuangan ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="bebankeuangan">Beban Keuangan</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="bebankeuangan" name="bebankeuangan" placeholder="Beban Keuangan ... ">
                    </div>

                </div>



                <div class="row">

                    <div class="col-25">
                        <label for="keuntungankerugianselisihkursmatauangasing">Keuntungan (Kerugian) Selisih Kurs Mata Uang Asing</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="keuntungankerugianselisihkursmatauangasing" name="keuntungankerugianselisihkursmatauangasing" placeholder="Keuntungan (Kerugian) Selisih Kurs Mata Uang Asing ... ">
                    </div>

                </div>



                <div class="row">

                    <div class="col-25">
                        <label for="pendapatanlainnya">Pendapatan Lainnya</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="pendapatanlainnya" name="pendapatanlainnya" placeholder="Pendapatan Lainnya ... ">
                    </div>

                </div>



                <div class="row">

                    <div class="col-25">
                        <label for="jumlahlabarugisebelumpajakpenghasilan">Jumlah Laba Rugi Sebelum Pajak Penghasilan</label>
                    </div>


                    <div class="col-75">
                        <input type="text" id="jumlahlabarugisebelumpajakpenghasilan" name="jumlahlabarugisebelumpajakpenghasilan" placeholder="Jumlah Laba Rugi Sebelum Pajak Penghasilan ... ">
                    </div>

                </div>



                <div class="row">

                    <div class="col-25">
                        <label for="pendapatanbebanpajak">Pendapatan Beban Pajak</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="pendapatanbebanpajak" name="pendapatanbebanpajak" placeholder="Pendapatan Beban Pajak ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="jumlahlabarugidarioperasiygdilanjutkan">Jumlah Laba Rugi Dari Operasi Yg Dilanjutkan</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="jumlahlabarugidarioperasiygdilanjutkan" name="jumlahlabarugidarioperasiygdilanjutkan" placeholder="Jumlah Laba Rugi Dari Operasi Yg Dilanjutkan ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="jumlahlabarugi">Jumlah Laba Rugi</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="jumlahlabarugi" name="jumlahlabarugi" placeholder="Jumlah Laba Rugi ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="jumlahlabarugikomprehensif">Jumlah Laba Rugi Komprehensif</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="jumlahlabarugikomprehensif" name="jumlahlabarugikomprehensif" placeholder="Jumlah Laba Rugi Komprehensif ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="labarugiygdapatdiatribusikankeentitasinduk">Laba Rugi Yg Dapat Diatribusikan Ke Entitas Induk</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="labarugiygdapatdiatribusikankeentitasinduk" name="labarugiygdapatdiatribusikankeentitasinduk" placeholder="Laba Rugi Yg Dapat Diatribusikan Ke Entitas Induk ... ">
                    </div>

                </div>



                <div class="row">

                    <div class="col-25">
                        <label for="labarugiygdapatdiatribusikankekepentingannon-pengendali">Laba (Rugi) Yang Dapat Diatribusikan Ke Kepentingan Non-Pengendali</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="labarugiygdapatdiatribusikankekepentingannon-pengendali" name="labarugiygdapatdiatribusikankekepentingannon-pengendali" placeholder="Laba (Rugi) Yang Dapat Diatribusikan Ke Kepentingan Non-Pengendali ... ">
                    </div>

                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="labarugipersahamdasardarioperasiygdilanjutkan">Laba (Rugi) Per Saham Dasar Dari Operasi Yang Dilanjutkan</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="labarugipersahamdasardarioperasiygdilanjutkan" name="labarugipersahamdasardarioperasiygdilanjutkan" placeholder="Laba (Rugi) Per Saham Dasar Dari Operasi Yang Dilanjutkan ... ">
                    </div>
                </div>



                <div class="row">

                    <div class="col-25">
                        <label for="penerimaandaripelanggan">Penerimaan Dari Pelanggan</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="penerimaandaripelanggan" name="penerimaandaripelanggan" placeholder="Penerimaan Dari Pelanggan ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="pembayarankepadapemasokatasbarangjasa">Pembayaran Kepada Pemasok Atas Barang Dan Jasa</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="pembayarankepadapemasokatasbarangjasa" name="pembayarankepadapemasokatasbarangjasa" placeholder="Pembayaran Kepada Pemasok Atas Barang Dan Jasa ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="kasdiperolehdarioperasi">Kas Diperoleh Dari (Digunakan Untuk) Operasi</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="kasdiperolehdarioperasi" name="kasdiperolehdarioperasi" placeholder="Kas Diperoleh Dari (Digunakan Untuk) Operasi ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="penerimaanbungadariaktivitasoperasi">Penerimaan Bunga Dari Aktivitas Operasi</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="penerimaanbungadariaktivitasoperasi" name="penerimaanbungadariaktivitasoperasi" placeholder="Penerimaan Bunga Dari Aktivitas Operasi ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="pembayaranbungadariaktivitasoperasi">Pembayaran Bunga Dari Aktivitas Operasi</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="pembayaranbungadariaktivitasoperasi" name="pembayaranbungadariaktivitasoperasi" placeholder="Pembayaran Bunga Dari Aktivitas Operasi ... ">
                    </div>

                </div>


                <div class="row">

                    <div class="col-25">
                        <label for="penerimaanpengembalianpajakpenghasilanaktivitasoperasi">Penerimaan Pengembalian (Pembayaran) Pajak Penghasilan Dari Aktivitas Operasi</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="penerimaanpengembalianpajakpenghasilanaktivitasoperasi" name="penerimaanpengembalianpajakpenghasilanaktivitasoperasi" placeholder="Penerimaan Pengembalian (Pembayaran) Pajak Penghasilan Dari Aktivitas Operasi ... ">
                    </div>

                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="jumlaharuskasbersihygdiperolehdariaktivitasoperasi">Jumlah Arus Kas Bersih Yang Diperoleh Dari (Digunakan Untuk) Aktivitas Operasi</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="jumlaharuskasbersihygdiperolehdariaktivitasoperasi" name="jumlaharuskasbersihygdiperolehdariaktivitasoperasi" placeholder="Jumlah Arus Kas Bersih Yang Diperoleh Dari (Digunakan Untuk) Aktivitas Operasi ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="penerimaandaripenjualanasettetap">Penerimaan Dari Penjualan Aset Tetap</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="penerimaandaripenjualanasettetap" name="penerimaandaripenjualanasettetap" placeholder="Penerimaan Dari Penjualan Aset Tetap ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="pembayaranuntukperolehanasettetap">Pembayaran Untuk Perolehan Aset Tetap</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="pembayaranuntukperolehanasettetap" name="pembayaranuntukperolehanasettetap" placeholder="Pembayaran Untuk Perolehan Aset Tetap ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="pembayaranuangmukainvestasi">Pembayaran Uang Muka Investasi</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="pembayaranuangmukainvestasi" name="pembayaranuangmukainvestasi" placeholder="Pembayaran Uang Muka Investasi ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="jumlaharuskasbersihygdiperolehdariaktivitas">Jumlah Arus Kas Bersih Yang Diperoleh Dari Aktivitas</label>
                    </div>

                    <div class="col-75">
                        <input type="text" id="jumlaharuskasbersihygdiperolehdariaktivitas" name="jumlaharuskasbersihygdiperolehdariaktivitas" placeholder="Jumlah Arus Kas Bersih Yang Diperoleh Dari Aktivitas ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="penerimaanpinjamanbank">Penerimaan Pinjaman Bank</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="penerimaanpinjamanbank" name="penerimaanpinjamanbank" placeholder="Penerimaan Pinjaman Bank ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="pembayaranpinjamanbank">Pembayaran Pinjaman Bank</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="pembayaranpinjamanbank" name="pembayaranpinjamanbank" placeholder="Pembayaran Pinjaman Bank ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="penerimaanutangpembiayaankonsumen">Penerimaan Utang Pembiayaan Konsumen</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="penerimaanutangpembiayaankonsumen" name="penerimaanutangpembiayaankonsumen" placeholder="Penerimaan Utang Pembiayaan Konsumen ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="pembayaranutangpembiayaankonsumen">Pembayaran Utang Pembiayaan Konsumen</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="pembayaranutangpembiayaankonsumen" name="pembayaranutangpembiayaankonsumen" placeholder="Pembayaran Utang Pembiayaan Konsumen ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="penerimaankaslainnyadariaktivitaspendanaan">Penerimaan (Pengeluaran) Kas Lainnya Dari Aktivitas Pendanaan</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="penerimaankaslainnyadariaktivitaspendanaan" name="penerimaankaslainnyadariaktivitaspendanaan" placeholder="Penerimaan (Pengeluaran) Kas Lainnya Dari Aktivitas Pendanaan ... ">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="jumlaharuskasbersihygdiperolehdariaktivitaspendanaan">Jumlah Arus Kas Bersih Yang Diperoleh Dari (Digunakan Untuk) Aktivitas Pendanaan</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="jumlaharuskasbersihygdiperolehdariaktivitaspendanaan" name="jumlaharuskasbersihygdiperolehdariaktivitaspendanaan" placeholder="Jumlah Arus Kas Bersih Yang Diperoleh Dari (Digunakan Untuk) Aktivitas Pendanaan ...">
                    </div>
                </div>


                <div class="row">
                    <div class="col-25">
                        <label for="jumlahkenaikanbersihkasdansetarakas">Jumlah Kenaikan (Penurunan) Bersih Kas Dan Setara Kas</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="jumlahkenaikanbersihkasdansetarakas" name="jumlahkenaikanbersihkasdansetarakas" placeholder="Jumlah Kenaikan (Penurunan) Bersih Kas Dan Setara Kas ... ">
                    </div>
                </div>
		    
		<div class="row">
                    <div class="col-25">
                        <label for="kasdansetarakasaruskasawalperiode">Kas Dan Setara Kas Arus Kas, Awal Periode</label>
                    </div>
                    <div class="col-75">
                        <input type="text" id="kasdansetarakasaruskasawalperiode" name="kasdansetarakasaruskasawalperiode" placeholder="Kas Dan Setara Kas Arus Kas, Awal Periode ... ">
                    </div>
                </div>


            </form>

        </div>

    </body>



</html>


```




