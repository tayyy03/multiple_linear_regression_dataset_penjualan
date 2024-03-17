# Multiple Linear Regression Analysis on Sales Data
This repository contains a Python notebook that performs multiple linear regression analysis on a sales dataset. The goal of this analysis is to understand how different factors affect sales.

## Libraries Used
NumPy: Used for efficient mathematical and logical operations on large, multi-dimensional arrays and matrices of numeric data.
Pandas: Used for data manipulation and analysis. It provides special data structures and data analysis tools, which makes working with structured data easy.
## Data
The data used in this analysis is stored in the (https://www.kaggle.com/datasets/dinishalikha/dataset-penjualan). The data is read using the pandas library.

## Code Structure
The code first imports the necessary libraries (numpy and pandas). It then lists all the files in the ../input/ directory using the os.walk function. The full path of each file is printed to the console.

## Output
<style type="text/css">
#T_3bf2d_row0_col0, #T_3bf2d_row1_col1, #T_3bf2d_row2_col2, #T_3bf2d_row3_col3, #T_3bf2d_row4_col4 {
  background-color: #023858;
  color: #f1f1f1;
}
#T_3bf2d_row0_col1, #T_3bf2d_row0_col3, #T_3bf2d_row1_col4, #T_3bf2d_row3_col0, #T_3bf2d_row3_col2 {
  background-color: #fff7fb;
  color: #000000;
}
#T_3bf2d_row0_col2 {
  background-color: #62a2cb;
  color: #f1f1f1;
}
#T_3bf2d_row0_col4 {
  background-color: #f8f1f8;
  color: #000000;
}
#T_3bf2d_row1_col0 {
  background-color: #fbf4f9;
  color: #000000;
}
#T_3bf2d_row1_col2 {
  background-color: #f7f0f7;
  color: #000000;
}
#T_3bf2d_row1_col3 {
  background-color: #ede8f3;
  color: #000000;
}
#T_3bf2d_row2_col0 {
  background-color: #589ec8;
  color: #f1f1f1;
}
#T_3bf2d_row2_col1 {
  background-color: #f5eef6;
  color: #000000;
}
#T_3bf2d_row2_col3 {
  background-color: #f9f2f8;
  color: #000000;
}
#T_3bf2d_row2_col4 {
  background-color: #c4cbe3;
  color: #000000;
}
#T_3bf2d_row3_col1 {
  background-color: #f0eaf4;
  color: #000000;
}
#T_3bf2d_row3_col4 {
  background-color: #dfddec;
  color: #000000;
}
#T_3bf2d_row4_col0 {
  background-color: #e6e2ef;
  color: #000000;
}
#T_3bf2d_row4_col1 {
  background-color: #f2ecf5;
  color: #000000;
}
#T_3bf2d_row4_col2 {
  background-color: #b3c3de;
  color: #000000;
}
#T_3bf2d_row4_col3 {
  background-color: #c8cde4;
  color: #000000;
}
</style>
<table id="T_3bf2d_">
  <thead>
    <tr>
      <th class="blank level0" >&nbsp;</th>
      <th class="col_heading level0 col0" >Hari</th>
      <th class="col_heading level0 col1" >Tanggal</th>
      <th class="col_heading level0 col2" >Kegiatan</th>
      <th class="col_heading level0 col3" >Curah Hujan (mm)</th>
      <th class="col_heading level0 col4" >Penjualan (pcs)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th id="T_3bf2d_level0_row0" class="row_heading level0 row0" >Hari</th>
      <td id="T_3bf2d_row0_col0" class="data row0 col0" >1.00</td>
      <td id="T_3bf2d_row0_col1" class="data row0 col1" >-0.00</td>
      <td id="T_3bf2d_row0_col2" class="data row0 col2" >0.54</td>
      <td id="T_3bf2d_row0_col3" class="data row0 col3" >-0.03</td>
      <td id="T_3bf2d_row0_col4" class="data row0 col4" >0.13</td>
    </tr>
    <tr>
      <th id="T_3bf2d_level0_row1" class="row_heading level0 row1" >Tanggal</th>
      <td id="T_3bf2d_row1_col0" class="data row1 col0" >-0.00</td>
      <td id="T_3bf2d_row1_col1" class="data row1 col1" >1.00</td>
      <td id="T_3bf2d_row1_col2" class="data row1 col2" >0.07</td>
      <td id="T_3bf2d_row1_col3" class="data row1 col3" >0.10</td>
      <td id="T_3bf2d_row1_col4" class="data row1 col4" >0.09</td>
    </tr>
    <tr>
      <th id="T_3bf2d_level0_row2" class="row_heading level0 row2" >Kegiatan</th>
      <td id="T_3bf2d_row2_col0" class="data row2 col0" >0.54</td>
      <td id="T_3bf2d_row2_col1" class="data row2 col1" >0.07</td>
      <td id="T_3bf2d_row2_col2" class="data row2 col2" >1.00</td>
      <td id="T_3bf2d_row2_col3" class="data row2 col3" >0.01</td>
      <td id="T_3bf2d_row2_col4" class="data row2 col4" >0.35</td>
    </tr>
    <tr>
      <th id="T_3bf2d_level0_row3" class="row_heading level0 row3" >Curah Hujan (mm)</th>
      <td id="T_3bf2d_row3_col0" class="data row3 col0" >-0.03</td>
      <td id="T_3bf2d_row3_col1" class="data row3 col1" >0.10</td>
      <td id="T_3bf2d_row3_col2" class="data row3 col2" >0.01</td>
      <td id="T_3bf2d_row3_col3" class="data row3 col3" >1.00</td>
      <td id="T_3bf2d_row3_col4" class="data row3 col4" >0.26</td>
    </tr>
    <tr>
      <th id="T_3bf2d_level0_row4" class="row_heading level0 row4" >Penjualan (pcs)</th>
      <td id="T_3bf2d_row4_col0" class="data row4 col0" >0.13</td>
      <td id="T_3bf2d_row4_col1" class="data row4 col1" >0.09</td>
      <td id="T_3bf2d_row4_col2" class="data row4 col2" >0.35</td>
      <td id="T_3bf2d_row4_col3" class="data row4 col3" >0.26</td>
      <td id="T_3bf2d_row4_col4" class="data row4 col4" >1.00</td>
    </tr>
  </tbody>
</table>
Dari tabel korelasi dan gambar pairplot, dapat dilihat bahwa :
- hari sangat memiliki hubungan yang lebih erat terhadap kegiatan marketing (0,53)
- kegiatan marketing memiliki hubungan yang erat terhadap penjualan (0,35)
- Curah hujan memiliki hubungan yang erat terhadap penjualan (0,26)

- hari dan tanggal tidak ada hubungan sama sekali karena nilainya 0
- hari dan curah hujan tidak ada hubungan sama sekali karena nilainya sangat kecil -0,03

Langkah terakhir adalah melakukan prediksi terhadap hasil penjualan paling optimal
array([163.31050106])

## How to Run
To run the code, click "run" or press "Shift+Enter".

## Contributions
Contributions, issues, and feature requests are welcome!

## License
This project is open source and available https://www.kaggle.com/code/mochmunirulichsan/multiple-linear-regression-dataset-penjualan.

## Contact
If you have any questions, feel free to reach out to me.
