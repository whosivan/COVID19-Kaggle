(1) Metadata for papers from these sources are combined: CZI, PMC, BioRxiv/MedRxiv. (total records 29500)
	- CZI 1236 records
	- PMC 27337
	- bioRxiv 566
	- medRxiv 361
(2) 17K of the paper records have PDFs and the hash of the PDFs are in 'sha'
(3) For PMC sourced papers, one paper's metadata can be associated with one or more PDFs/shas under that paper - a PDF/sha correponding to the main article, and possibly additional PDF/shas corresponding to supporting materials for the article.
(4)	13K of the PDFs were processed with fulltext ('has_full_text'=True)
(5) Various 'keys' are populated with the metadata:
	- 'pmcid': populated for all PMC paper records (27337 non null)
	- 'doi': populated for all BioRxiv/MedRxiv paper records and most of the other records (26357 non null)
	- 'WHO #Covidence': populated for all CZI records and none of the other records (1236 non null)
	- 'pubmed_id': populated for some of the records
	- 'Microsoft Academic Paper ID': populated for some of the records




### 2020-03-20
---CHANGES---
* normalized doi, authors, title, abstract strings
* merged redundant rows in metadata file on doi, pmcid, and pubmed_id
* metadata sha column can now include multiple files (some PMC files have multiple associated PDFs)
* added column in metadata file "full_text_file" to signal the tar.gz file in which the full text json resides
---SUMMARY---
total metadata rows: 44220
custom_license: 16959 full text (new: 15533)
noncomm_use_subset: 2353 full text (new: 385)
comm_use_subset: 9118 full text (new: 128)
biorxiv_medrxiv: 885 full text (new: 110)




### 2020-03-27
---CHANGES---
* added column "cord_uid" (this persistent identifier is a 8-char alphanumeric string unique to each entry)
* added column "url" (URL to paper landing page where available)
* normalized publication date, dois
* adjusted deduplication logic slightly (affects 3 papers)
* removed some entries that correspond to indices or table of contents

---SUMMARY---
total metadata rows: 45774
biorxiv_medrxiv: 1053 full text (new: 194, removed: 26)
comm_use_subset: 9315 full text (new: 210, removed: 13)
custom_license: 20657 full text (new: 4218, removed: 520)
noncomm_use_subset: 2350 full text (new: 6, removed: 9)



### 2020-04-03
---CHANGES---
* added PMC XML parses; available under metadata file column "has_pmc_xml_parse"
* renamed "has_full_text" metadata column to "has_pdf_parse"
* restructured tar.gz outputs, example new directory structure:
|-- comm_use_subset
   |-- pmc_json (contains all JSON derived from PMC XML parses; filenames are PMC_ID.xml.json)
   |-- pdf_json (contains all JSON derived from PDF parses)

NOTE: some papers have both PMC XML and PDF parses

---SUMMARY---
total metadata rows: 47298
47296 CORD UIDs (new: 1524, removed: 2)

biorxiv_medrxiv:
  PDF - 1342 full text (new: 348, removed: 59)
comm_use_subset:
  PDF - 9365 full text (new: 70, removed: 20)
  PMC - 8995 full text (new: 8995, removed: 0)
custom_license:
  PDF - 23152 full text (new: 2541, removed: 46)
  PMC - 4773 full text (new: 4773, removed: 0)
noncomm_use_subset:
  PDF - 2377 full text (new: 54, removed: 27)
  PMC - 2093 full text (new: 2093, removed: 0)



### 2020-04-10
---CHANGES---
* minor change to metadata deduplication logic

---SUMMARY---
total metadata rows: 51078
51045 CORD UIDs (new: 3786, removed: 38)

biorxiv_medrxiv:
  PDF - 1625 full text (new: 353, removed: 70)
comm_use_subset:
  PDF - 9524 full text (new: 174, removed: 15)
  PMC - 9148 full text (new: 174, removed: 21)
custom_license:
  PDF - 26505 full text (new: 3647, removed: 294)
  PMC - 7802 full text (new: 3081, removed: 52)
noncomm_use_subset:
  PDF - 2490 full text (new: 130, removed: 17)
  PMC - 2217 full text (new: 128, removed: 4)



### 2020-04-17
---CHANGES---
* no changes

---SUMMARY---
total metadata rows: 52398
52365 CORD UIDs (new: 1320, removed: 1)

biorxiv_medrxiv:
  PDF - 1934 full text (new: 426, removed: 117)
comm_use_subset:
  PDF - 9557 full text (new: 104, removed: 71)
  PMC - 9189 full text (new: 97, removed: 56)
custom_license:
  PDF - 27220 full text (new: 882, removed: 167)
  PMC - 8018 full text (new: 224, removed: 8)
noncomm_use_subset:
  PDF - 2466 full text (new: 23, removed: 47)
  PMC - 2212 full text (new: 22, removed: 27)



### 2020-04-24
---CHANGES---
* no changes

---SUMMARY---
total metadata rows: 57366
57332 CORD UIDs (new: 4988, removed: 22)

biorxiv_medrxiv:
  PDF - 2278 full text (new: 492, removed: 148)
comm_use_subset:
  PDF - 9769 full text (new: 253, removed: 41)
  PMC - 9390 full text (new: 233, removed: 32)
custom_license:
  PDF - 31376 full text (new: 4355, removed: 199)
  PMC - 10615 full text (new: 2630, removed: 33)
noncomm_use_subset:
  PDF - 2518 full text (new: 68, removed: 16)
  PMC - 2258 full text (new: 56, removed: 10)


### 2020-05-01
---CHANGES---
* added arXiv as a source of papers
* added column arxiv_id in metadata.csv file to store arxiv identifiers

---SUMMARY---
total metadata rows: 59887
59851 CORD UIDs (new: 2522, removed: 4)

arxiv:
  PDF - 787 full text (new: 787)
biorxiv_medrxiv:
  PDF - 2670 full text (new: 543, removed: 151)
comm_use_subset:
  PDF - 9918 full text (new: 183, removed: 34)
  PMC - 9540 full text (new: 171, removed: 21)
custom_license:
  PDF - 32450 full text (new: 1295, removed: 221)
  PMC - 11000 full text (new: 430, removed: 45)
noncomm_use_subset:
  PDF - 2584 full text (new: 79, removed: 13)
  PMC - 2311 full text (new: 61, removed: 8)




### 2020-05-12
---CHANGES---

NOTE: THERE ARE SIGNIFICANT BREAKING CHANGES THIS WEEK. 
      PLEASE READ CAREFULLY.

* moving to one single full text release file (document_parses.tar.gz) 
  that combines the json parses from all *.tar.gz files from 
  previous releases 
* consolidated metadata columns `has_pdf_parse` and `full_text_file` 
  into column `pdf_json_files`, which now stores the relative paths to the
  corresponding *.json files, 
  e.g. document_parses/pdf_json/e3d0d482ebd9a8ba81c254cc433f314142e72174.json
* consolidated metadata columns `has_pmc_xml_parse`, `full_text_file` and
  pmcid lookup into column `pmc_json_files`, which now stores the relative
  paths to the corresponding *.xml.json files,
  e.g. document_parses/pmc_json/PMC125375.xml.json
* renamed metadata columns: 
    "Microsoft Academic Paper ID" -> "mag_id"
    "WHO #Covidence" -> "who_covidence_id"
* added HTML table parses for many files; these are in the PDF json parses 
  where available, under key "ref_entries", type "table", key "html". this 
  rollout is incremental, and more tables will be added as they become 
  available.
  
SEE FAQ FOR DETAILED INFORMATION: 
https://discourse.cord-19.semanticscholar.org/t/faqs-about-cord-19-dataset/94
 

---SUMMARY---
total metadata rows: 63571
CORD UIDs (new: 3691, removed: 15)

Full text:
  PDF - 51882 json (new: 4950, removed: 1492)
  PMC - 33503 json (new: 13989, removed: 3337)


### 2020-05-19
---CHANGES---

Added Medline paper source
Changed metadata column `url` to a ;-joined list
Added Semantic Scholar paper identifier where available to metadata column `s2_id`
	The s2_id can be resolved to the Semantic Scholar paper page using the API at https://api.semanticscholar.org/


---SUMMARY---
total metadata rows: 128492
CORD UIDs (new: 71901, removed: 7266)

Full text:
  PDF - 59566 json (new: 15396, removed: 7704)
  PMC - 43753 json (new: 10259, removed: 9)
