# London Lives Pauper Examinations

Contents
---------

-   Description
-   Background
-   The examinations
-   Methods and caveats
-   Data summary
-   Acknowledgments
-   License
-   Citation
-   Future plans


This data is released under a Creative Commons Attribution-ShareAlike 4.0 International Licence.

[![License: CC BY-SA 4.0](https://licensebuttons.net/l/by-sa/4.0/80x15.png)](http://creativecommons.org/licenses/by-sa/4.0/)

Description
----------------

Textual data and documentation relating to approximately 28000 individuals in 10700 examinations, originally digitised as part of [London Lives](http://www.londonlives.org).

February 2026: 

- reinstated about 4200 names that had been accidentally omitted from the llep_names table (I have no idea how this happened!)
- converted TSV files to CSV 
- some content updates and corrections

September 2018: added plain text files of the examinations

Supplementary data (March 2017): smaller dataset of [St Clement Danes removal orders](https://github.com/sharonhoward/llep/tree/master/removal_orders).


Background
------------

[London Lives 1690-1800: Crime, Poverty and Social Policy in the
Metropolis](http://www.londonlives.org) is an online resource
providing 'a wide range of primary sources about eighteenth-century
London, with a particular focus on plebeian Londoners'. It contains more
than 240,000 manuscript and printed pages from eight London archives,
including parochial **Pauper Settlement, Vagrancy and Bastardy Examinations**. 

Individual parishes used examinations conducted by one or two Justices of the Peace for three distinct purposes:

-   to determine the settlement of an individual (a claim to a right of legal residence and relief in a parish)
-    to police bastardy, and as a basis for reclaiming the costs of supporting illegitimate children from the father
-    as a contribution to the wider county prosecution of vagrancy. 

The vast majority of examinations concerned pauper settlements (and most bastardy examinations were of poor women, whose offspring were 'likely to become chargeable' to a parish), and so this project uses the more concise term **pauper examinations** even though it's not technically accurate in all cases.

London Lives has two series of pauper examinations, from the parishes of St Botolph Aldgate and St Clement Danes. It also contains pauper examinations in other series, but I have not (yet) attempted to extract these. 




Methods and caveats
-------------------

### Essential background reading: 

- [London Lives technical methods](http://www.londonlives.org/about/project#toc6)
- [Pauper Examinations](http://www.londonlives.org/about/ep)

See also: [Settlement](https://www.londonlives.org/about/settlement) - [Bastardy](https://www.londonlives.org/about/bastardy) - [Vagrancy](https://www.londonlives.org/about/vagrancy)

### The source data

51 XML files, part of the data for the searchable online resource at www.londonlives.org (v1.1, released April 2012). These files represent examinations from two parishes, St Botolph Aldgate (BA) and St Clement Danes (CD).

The material in London Lives was transcribed using a method known as [double rekeying](http://www.londonlives.org/about/project#toc8), in which two (non-academic) typists transcribe text, the two versions are compared and only where they differ does any further manual checking take place. It is not as accurate as traditional academic standards of transcription and proofreading, but unfortunately that is not a practical option for transcription of such large amounts of text. The accuracy rate for London Lives is approximately 98-99% (at character level), but it can vary considerably between documents.

The rekeyed texts were then marked up for searching, using a combination of automated and manual tagging, for various types of information: the names of people and places, occupations and dates. There is also structural markup for features such as text in margins, deleted, obscured or illegible text, text continuing across page breaks, and so on. 

The markup did not, however, include information about document structures. File categorisation was based on the original document series' archival organisation; there is no real structuring information between this type of generic classification and the single page. 


### Data collection

#### Locating examinations

The majority of pauper examinations consist of a single page in the original bound volumes - but not all of them. Some take up multiple pages; conversely some are very short and more than one examination (not necessarily related in any way) can appear on a single page. So, in order to group the subjects of each examination together accurately, the first task is to find both the beginning and end of every examination. 

Fortunately, the examinations - as legal documents - followed some strict conventions, and most of the examinations were written by well-trained scribes using consistent spelling forms. There were, however a number of possible minor variants (and identifying the end of an examination could be slightly trickier than finding the starting point). 

**Opening examples**:

* Middlesex Richard Macguir Maketh oath That... 
* Middlesex ss Catherine Small the widow of William Small maketh Oath that... 
* Middlesex Margt Doleman Wido. of John Doleman who hath been dead upwards of three Years upon Oath saith...
* Middlesex ss. The Examination of Sarah Mills of the Parish of Saint Botolph without Aldgate in the said County Singlewoman taken on Oath...
* Middx & Westmr John Herbert aged about Thirty Nine years on his Oath says...

**Characteristics**:

1. The majority of examinations begin with "Middlesex" or "Middlesex and Westminster" (or abbreviated forms). Following this:
2. The examinant almost always  "saith", "upon his/her oath says" or "maketh oath".
3. In some cases (usually bastardy or vagrancy exams), the text begins "The examination of ..." or "The voluntary examination of..." 

**Closure**:

Normally, the end of an examination can simply be located just before the beginning of the next one. But this could not always be assumed, as sometimes examinations were interspersed with other notes about cases, names that might or might not be related, and so on. There were also indexes at the end of some volumes. So a certain amount of care could be needed to ensure the end of examinations was identified accurately. 

Not all examinations were signed, but nearly all (apart from a very few fragmentary examinations) contained slight variants of the lines below at the end of the main text, and just before signatures (or the space where signatures would have been filled in).

**Examples**:

* Sworn the 10th. Day of May 1756 before}  
* Sworn this. 30. day of Novemr 1786 before


#### Disambiguation of names

Initial identification of names in examinations was straightforward, using the existing London Lives tagging. Almost all full names (names that have at least one given and one surname present) in these files have been accurately tagged, although there are occasional omissions. The omissions, when spotted, have only been rectified for examinants and other significant individuals.

The next task (which turned out to be far more time-consuming than expected) was to remove duplicate mentions of the same person within each examination, whilst ensuring I retained different individuals who shared the same name. I underestimated initially the extent to which 18th-century parents named their children after themselves. 

There may have been a few errors along the way, either in failing to identify a duplicate or deleting a non-duplicate. 

#### Identification of examinants and other people

The structure of the examinations also made it easy to identify examinants. However, something I also underestimated at the beginning of the project was the number of examinations in which the examinant was *not* the pauper who was the actual subject of the examination (most often because the pauper was a young child, physically ill or mentally incapacitated). This proved less straightforward than initially anticipated since the examinations don't always explicitly state that the examination was "on behalf of" the pauper concerned. An alternative wording was that the examinant "well knows" the pauper, but there are other less identifiable cases, and probably still some in the data that I failed to identify.   

Occasionally an examinant was examined both for him/herself *and* on behalf of another individual, or conversely an examination could have both the pauper *and* a witness on their behalf speaking.

Some of the witness-examinants were parish officials, in which case I've removed them from the dataset altogether. Others have been retained (often they're relatives) but identified as such.

The examinations contain many more names than those of the examinants - parents, children, siblings, employers, the alleged fathers of bastards, and so on. At the moment only some of these are specifically labelled, where it's fairly straightforward to do so (children, employers). I'm working on relationships data for future releases.


#### Excluding magistrates and parish officials

The names of magistrates, if present, appear in very predictable places (usually at the very end of the examination). Parish officials are less common but usually fairly straightforward to identify. Wherever possible, these have been removed from the dataset. (A version of the data that includes them can be made available on request, but it should be borne in mind that magistrates' names were often not tagged because they signed with an initial rather than full first name.)


#### Finding additional information about examinations and individuals

* Using existing London Lives tagging and user-contributed roles

The St Botolph Aldgate examinations were the very first documents the London Lives project tagged, as a test run for manual tagging and as training data for automated tagging. As a result, they were checked and marked up more exhaustively than most other documents. In particular, place and occupation/status tagging were comprehensively tagged and manually linked to individual names to an extent that turned out to be impracticable for the project as a whole. All of this information could be imported directly into the dataset.

Dates were also tagged well in both sets of examinations, but a little care was needed to identify the date of an examination (usually by positioning in the text) rather than earlier dates mentioned by an examinant.

Some tagged names in London Lives have had "roles" assigned to them manually by project members and site users. (This information is not part of the XML markup.) This was particularly useful in the case of the mothers of bastard children, and less systematically so in other cases. 

* Keyword and proximity searches around tagged names

Additional information (or information missed by the original tagging) was obtained primarily by used of keyword searches in proximity to a tagged name: eg, "widow", "spinster/single woman" or "wife of" immediately after a woman's name, and occupations after a man's name. 

Because pauper examinations are relatively formulaic, it was possible to use this to extract a variety of kinds of information with some confidence in reliability of the information found (and that it was associated with the right person), although if the information was written down in less standard ways it would be less likely to be found, eg:

   - Ages
   - Bastardy
   - Information about settlements (work in progress)
   - Relationships (too unreliable and messy to release at present)

Some other information - eg, about irregular marriages and separations, and most tagged place names  - has not (yet) been associated with specific individuals but is made available as examination-level data. Only a small proportion of all tagged place data (primarily parishes and towns) in the XML files has been included here. 



The Data 
--------

### General notes

The current release is 3.0, February 2026. 

The accuracy of the data is not guaranteed; some errors in the data are likely, because most entries have not been individually checked. Apart from errors in the original London Lives data, some will have been introduced in the extraction of information from complex narrative texts. Please read the **methods** section carefully before using the data! 

The data tables are supplied in .csv (comma separated values) format which can be readily imported into spreadsheets and database software.

### Data fields

#### In all data tables
 
* **exam_id** is the unique identifier for each **examination** and can be used to link tables in a database. It's almost always the same as **ll_img** (the first image in a multi-page examination), but adds an extra identifier where there are multiple examinations on one page.
* **ll_img** is the image reference that can be used to locate individuals on the [London Lives](http://www.londonlives.org) website (using the reference search). In names data it may not always be the first page of an examination.
* **ll_url** is based on ll_img: it will take you straight to the relevant page when pasted into a browser (spreadsheets may automatically display it as a clickable hyperlink).

Some examination dates (**exam_date**) are approximate. Not all examinations were dated; some gave month and year only. An approximate date for undated examinations was inferred from their location in a volume. 

All the month-year dates are now dated as "yyyy-mm-01" (rather than -00) to avoid problems when importing with some statistical software. The exam_date_precision column has been added to differentiate them.


#### llep_exams

*Summary information for each examination.*


| field | description |
|------|--------------|
| exam_id | unique examination ID |
| ll_img | London Lives (first) image reference |
| exam_date | date of examination yyyy-mm-dd |
| exam_date_precision | ymd or ym |
| parish_code | two letter parish code |
| examinants | list of examinants |
| ex_on_behalf | witness(es) examined on behalf of pauper |
| ll_url | London Lives URL |


#### llep_names

*Names data for examinants and subjects of examinations, their families and some other associates (especially employers).*

Magistrates, parish officials and a small number of elite individuals have been omitted.

**name_id** is the unique identifier for individual names. **exam_id**  groups together people in the same examination. There has been no attempt to link individuals *between* examinations (it's not uncommon to have more than one examination for the same person/people). 

In **exam_type**, bastardy and vagrancy are narrowly (legally) defined (and the type 'settlement' is a residual category for all other examinations). However, **bastardy_relationship** is used to record bastard mothers, (alleged) fathers and their offspring in *all* exams. 

The data about settlements should be treated with some caution and considered a work in progress; although I think it's mostly reliable, it's far from complete.

| field | description |
|------|------------------|
| name_id | London Lives unique name identifier |
| exam_id | examination ID |
| exam_parish | St Botolph Aldgate or St Clement Danes |
| exam_date | date of examination yyyy-mm-dd |
| exam_date_precision | ymd or ym |
| exam_type | settlement, bastardy or vagrancy.  |
| given | first name(s) |
| surname | family name(s) |
| altname | aliases, alternative names/spellings, and maiden names for married women |
| gender | derived from first names |
| age | age in years (infants under 6 months = 0, 6-12 months = 1) |
| year_of_birth | approximated, derived from age and exam date |
| date_of_birth | as given in examination (there are not many of these) |
| is_dead | 'y' = mentioned as deceased at time of examination |
| occup_status | occupation or status |
| other_status | mainly 'master' (used for both male and female employers), 'child'; a few 'prisoner' or 'convict' |
| exam_role1 |  examinant, examinant on behalf of pauper, pauper on behalf |
| exam_role2 | pauper, witness, bastardy, vagrant |
| incapacity | the reason (stated or inferred) that a pauper is unable to give evidence on their own behalf |
| bastardy_relationship | bastardmother, bastardfather, bastard  |
| bf_description | rich physical descriptions of putative fathers, given in some late bastardy cases |
| settlement | stated sources of eligibility for settlement: mainly apprenticeship, servant, rental |
| geo | places (mainly parishes) mentioned in the examination |
| snip_txt | a snippet of text in the London Lives transcription around the name, for context and to aid identification in London Lives where different people in an examination share the same name |
| ll_img | London Lives image reference |
| ll_url | London Lives URL |



#### llep_irregular_union_disunion

*Examinations that contain references to bigamous, irregular, clandestine or broken marriages and extramarital cohabitations.* 

The category 'separation' includes both explicit mentions of desertion and slightly more ambiguous (not necessarily permanent) absences.

| field | description |
|------|------------------|
| exam_id | unique examination ID |
| ll_img | London Lives image reference |
| exam_date | date of examination |
| exam_date_precision | ymd or ym |
| iud_type | currently includes: bigamy, catholic, cohabit, fleet, separation. There can be more than one for the same examination. |
| b_c | 'y' if there are any bastard children |
| snip_txt | short snippet of the opening paragraph of the examination text, which may contain further detail |
| ll_url | London Lives URL |


#### llep_texts 

This zipped archive contains plain text files of the examinations, 1 file per examination, organised into one folder for St Botolph Aldgate (2597 files) and one for St Clement Danes (8132 files). The **exam_id** is used to name each file. The text was extracted from the XML files using the Python library BeautifulSoup4.


Acknowledgments
---------------------

The dataset has been created using the transcriptions of the documents published at London Lives. I am deeply grateful to Tim Hitchcock and Bob Shoemaker, the London Lives project directors, for agreeing to share the data.

The original documents are held at the London Metropolitan Archives and the Westminster Archives Centre.

The London Lives project (under the name Plebeian Lives) was funded by the Economic and Social Research Council between 2006-2010.


License
---------

The dataset and all accompanying documentation are licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

This means that you are free to copy and redistribute the material in any medium or format; and to remix, transform, and build upon the material for any purpose, even commercially, providing you follow the terms of the licence:

-    You must give appropriate credit, provide a link to the license, and indicate if changes were made.
-    If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.


Citation
--------

**Suggested citation**:

Sharon Howard, The London Lives Pauper Examinations Database, version 3.0 (2026), based on data from *www.londonlives.org*.


Future plans
-------------

* Completion of settlement data
* Addition of data about *regular* marriages (hopefully including dates and places)
* Relationships data
* Attempt extracton of early 18th-century St Clement Danes Register of Pauper Settlement and Bastardy Examinations
* Identify and extract pauper examinations and related material in the London Lives Sessions Papers
* Linkage to related documents in London Lives, such as [Bastardy Bonds](https://www.londonlives.org/about/wb) and [Registers of Removed Paupers](https://www.londonlives.org/about/rv)


[![zenodo](https://zenodo.org/badge/51260676.svg)](https://zenodo.org/badge/latestdoi/51260676)
