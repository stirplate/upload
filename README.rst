Stirplate.io Data Upload Helper
===============================

*Current version:* **v1.4.0**


Sequencing data may be sent to Stirplate several ways.

1. Manual data upload via `stirplate.io <https://stirplate.io>`__.
2. **RECOMMENDED**: Automatic upload from a local computer directly to
   Stirplate without user interaction (outlined in this document).

Installation:
--------------

-  To setup and run automated data upload to Stirplate, be sure you have
   your Stirplate User Credentials (please contact keith@stirplate.io to
   obtain these).
-  Python 2.7.x (untested on Python >= 3).
-  ::

      pip install stirplate

-  A ``stirplate`` executable will be added to your system path.


Configure Access:
=================

Configure your Stirplate Access Credentials.

1. **Interactive**: Simply type:

   ::

      stirplate configure

2. **Automatic**: (Recommended) "Install" the supplied configuration
   file automatically from a downloaded config file:

   ::

      stirplate configure --install /path/to/stirplate/config

RNA-Seq protocol:
=================

There are two ways to run the data upload helper for the Stirplate
RNA-Seq (DESeq2) protocol:

1. **Interactive**. Simply type:

   ::

      stirplate rna

   -  You will be prompted for the input directory containing your
      sequencing data, as well as additional meta data (aligner [TopHat, STAR], species, single
      stranded protocol) information.

2. **Automatic**. Simply run:

   ::

       stirplate rna
       --aligner star
       --directory /path/to/input/sequencing/data/
       --project_name MyProjectName
       --species SPECIES


   -  Aliger choices are: ``tophat`` (default), and ``star``.
   -  Species choices are: ``C_ELEGANS`` (worms), ``D_RERIO``
      (zebrafish), ``H_SAPIENS`` (humans), ``M_MUSCULUS`` (mouse),
      ``R_NORVEGICUS`` (rat), ``B_TAURUS`` (cow), ``C_FAMILIARIS`` (dog), or ``E_CABALLUS`` (horse).
   -  If the experiment was performed using a single strand protocol,
      pass the ``--single_stranded_protocol`` flag as well.
   -  Upon running, all files in your input sequence data ``directory``
      will be uploaded to Stirplate.io. The uploading is optimized for
      speed so your data will be transferred in the least amount of
      time. **Processing will begin at Stirplate as soon as the last
      file transfer has completed**.

DNA-Seq protocol:
=================

There are two ways to run the data upload helper for the Stirplate
RNA-Seq (DESeq2) protocol:

1. **Interactive**. Simply type:

   ::

      stirplate dna

   -  You will be prompted for the input directory containing your
      sequencing data, as well as additional meta data (aligner [TopHat, STAR], species, single
      stranded protocol) information.

2. **Automatic**. Simply run:

   ::

       stirplate dna
       --directory /path/to/input/sequencing/data/
       --interval_file /path/to/input/sequencing/data/intervals.interval_list
       --project_name MyProjectName
       --species SPECIES


   -  Species choices are currently:  ``H_SAPIENS`` (humans). More available on request. Email keith@stirplate.io.
   -  Upon running, all files in your input sequence data ``directory``
      will be uploaded to Stirplate.io. The uploading is optimized for
      speed so your data will be transferred in the least amount of
      time. **Processing will begin at Stirplate as soon as the last
      file transfer has completed**.

Data Upload and Storage only protocol:
======================================

There are two ways to run the data upload helper for the Stirplate
(sotrage only) protocol:

1. **Interactive**. Simply type:

   ::

      stirplate storage

   -  You will be prompted for the input directory containing your
      sequencing data.

2. **Automatic**. Simply run:

   ::

       stirplate storage
       --directory /path/to/input/sequencing/data/
       --project_name MyProjectName

   -  Upon running, all files in your input sequence data ``directory``
      will be uploaded to Stirplate.io. The uploading is optimized for
      speed so your data will be transferred in the least amount of
      time. **Processing will begin at Stirplate as soon as the last
      file transfer has completed**.

Help
====

Troubleshooting install
-----------------------

If `pip install stirplate` gives you permissions error, you can install the package as either:

   - Root user: `sudo pip install stirplate`
   - Current user: `pip install --user stirplate`


Troubleshooting usage
---------------------
At any point you may get additional command line usage help by typing:

-  ``stirplate -h``
-  ``stirplate rna -h``
-  ``stirplate dna -h``

Email keith@stirplate.io for any futher questions.
