---
layout: page
title: Data
permalink: data
show-title: false
---

<center><h1> Access the Dataset </h1></center>

<center><h2>Boston Police Station Number One (North End) Monthly Reports <br> (June 1854-December 1859)</h2></center>

<center><a href="https://raw.githubusercontent.com/BCDigSchol/policedata/main/data/data_download.zip" target="_blank" rel="noopener" title="Download the Zip file">
  <button style="padding: 10px 20px; background-color: #4CAF50; color: white; border: none; border-radius: 5px; cursor: pointer;">
Download CSV
  </button>
</a>
</center>


In this dataset, we have compiled the  monthly logs of Captain Edward H. Savage (1812-1893). It is derived from the archives available at [Burns Library](https://libguides.bc.edu/burns) at Boston College. We have turned the ledger of Captain Savage into a spreadsheet which allows it to be machine-readable and easy to work with. We have done this as follows:  

For instance, if the entry for June 1854 appears as follows: 

<p align="center">
    <img src="assets/img/archive_screenshot.png" />
</p>


We have tabulated the data in the following format:

<p align="center">
    <img src="assets/img/data_screenshot.png" />
</p>

<p><br><br></p>

## Preview of the Dataset

<table id="data-table" class="display"></table>

<link rel="stylesheet" href="https://cdn.datatables.net/1.13.6/css/jquery.dataTables.min.css">
<script src="https://code.jquery.com/jquery-3.7.0.min.js"></script>
<script src="https://cdn.datatables.net/1.13.6/js/jquery.dataTables.min.js"></script>

<script>
fetch('{{ "/data/data.json" | relative_url }}')
  .then(response => response.json())
  .then(data => {
    const columns = Object.keys(data[0]).map(key => ({ title: key, data: key }));
    $('#data-table').DataTable({
      data: data,
      columns: columns,
      pageLength: 25,
      lengthMenu: [10, 25, 50, 100],
    });
  });
</script>

<p> <br> </p>


<center><a href="https://raw.githubusercontent.com/BCDigSchol/policedata/main/data/data_download.zip" target="_blank" rel="noopener" title="Download the Zip file">
  <button style="padding: 10px 20px; background-color: #4CAF50; color: white; border: none; border-radius: 5px; cursor: pointer;">
Download CSV
  </button>
</a>
</center>


The dataset can feel overwhelming at first, if you don't know where to start we would recommend you to check out a few of the [interesting categories](/policedata/interesting_discoveries) page for some ideas. Or you can also check out our [examples](/policedata/example1).




    

## Notes about data:

We had to merge a few categories. We find it pertinent to share these details alongwith our reasoning of doing so. 
However, if you want to know how the data was presented exactly in the record-book - please refer to the [Burns Library Archive's scans](https://findingaids.bc.edu/repositories/2/archival_objects/47581) directly. Here is a table of some of the merged categories that we aren't too sure of. 

First set of changes are:

| Category | Merged Category | Explanation |
|---|---|---|
| Otherwise | Absent sick and otherwise | In the interest of helping researchers identify broader patterns from the data, <br>we merged the categories of "time lost by sickness" and <br>"otherwise" into absent sick and otherwise. You can check the data sample sheet <br>to see unmerged values for these categories |
| Time lost by sickness | Absent sick and otherwise | Same as above |
| Truants | Stubborn & Truant Children | We strongly suspected that "truants" was simply a shortened version of the "stubborn<br>and truant children" category so we merged the former to the latter. <br>we merged the categories of "time lost by sickness" and <br>"otherwise" into absent sick and otherwise. You can check the data sample sheet <br>to see unmerged monthly values for these categories. |
| Dangerous Buildings repaired | Dangerous buildings reported/secured | In the interest of helping researchers identify broader patterns from the data, <br>we merged the categories of "dangerous building reported" and "dangerous buildings <br>secured" into a single category named "dangerous building reported/secured."  <br>You can check the data sample sheet  to see unmerged monthly values for these categories. |
| Dangerous places secured | Dangerous buildings reported/secured | Same as above |
| Defective fluid lamps reported | Defective Street Lamps Repaired/Reported | In the interest of helping researchers identify broader patterns from the data, <br>we merged the categories of "defective fluid lamps reported" and  "defective gas lamps reported" into a single category <br>named "defective street lamps reported."  You can check the data sample sheet to see <br>unmerged monthly values for these categories. |
| Defective gas lamps reported | Defective Street Lamps Repaired/Reported | Same as above |
| Defective Street Lamps Repaired | Defective Street Lamps Repaired/Reported | Same as above |


Other non-substantial, but important to note changes are:

Sometimes we changed a few categories to a standardised form. For instance: "Cases referred to Grand Jury" often appears in the later pages of the record book as just "Grand Jury". Usually, in earlier dates - we find the longer version of the category, but at later dates they are shortened, most likely to save space. Generally, we have tried to be as honest and close to the record book as possible. But at times, we made a few decisions like this so that we could aggregate the data over the whole time period. Such standardisation allows us to see larger patterns as shown in the [examples](/policedata/example1) page. For any such discrepancies, always refer to the scans or the archive as the authoritative source.  
