# utl-rename-variables-in-master-table-using-a-meta-table-of-names-and-newames-using-macro-arrays
Rename variables in master table using a meta table of names and newames using macro arrays
    %let pgm=utl-rename-variables-in-master-table-using-a-meta-table-of-names-and-newames-using-macro-arrays;

    %stop_submission

    Rename variables in master table using a meta table of names and newames using macro arrays

    Related repos on the end

    github
    https://tinyurl.com/3x9pm263
    https://github.com/rogerjdeangelis/utl-rename-variables-in-master-table-using-a-meta-table-of-names-and-newames-using-macro-arrays

    communities.sas
    https://tinyurl.com/mrxwk2w8
    https://communities.sas.com/t5/SAS-Programming/Dynamically-rename-a-table-s-variable-names-with-another-table-s/m-p/821158#M324191

    /**************************************************************************************************************************/
    /*            INPUT                    |          PROCESS                         |         OUTPUT                        */
    /*            =====                    |          =======                         |         ======                        */
    /*                                     |                                          |                                       */
    /* SD1.META RENAME LIST                | %array(_old,data=sd1.meta,var=oldNam);   | RENAMED BLUE, GREEN & ORANJE          */
    /*                                     | %array(_new,data=sd1.meta,var=newNam);   |                                       */
    /* OLDNAM    NEWNAM                    |                                          |       WAS             WAS   WAS       */
    /*                                     | proc datasets lib=sd1;                   |       BLUE            GREEN ORANGE    */
    /* Blue       V345                     |   modify master;                         | BLACK V345 BROWN GRAY V678  V546      */
    /* Green      V678                     |   rename                                 |                                       */
    /* Orange     V546                     |     %do_over(                            |   10   20    30   40   50    60       */
    /*                                     |       _old _new                          |   11   22    33   44   55    66       */
    /*                                     |      ,phrase=%str(?_old = ?_new))        |                                       */
    /* SD1.MASTER RENAME USING META DATA   | ;run;quit;                               |                                       */
    /*                                     |                                          |                                       */
    /* BLACK BLUE BROWN GRAY GREEN ORANGE  | If you want the generate code            | IN LOG                                */
    /*                                     |                                          |                                       */
    /*   10   20    30   40    50    60    | data _null_;                             | Blue=V345                             */
    /*   11   22    33   44    55    66    |  %do_over(_old _new                      | Green=V678                            */
    /*                                     |   ,phrase=%str(put "?_old=?_new";));     | Orange=V546                           */
    /* options                             | run;quit;                                |                                       */
    /*   validvarname=upcase;              |                                          |                                       */
    /* libname sd1 "d:/sd1";               |                                          |                                       */
    /* data sd1.meta;                      |                                          |                                       */
    /*  input oldNam$ NewNam$;             |                                          |                                       */
    /* cards4;                             |                                          |                                       */
    /* Blue V345                           |                                          |                                       */
    /* Green V678                          |                                          |                                       */
    /* Orange V546                         |                                          |                                       */
    /* ;;;;                                |                                          |                                       */
    /* run;quit;                           |                                          |                                       */
    /*                                     |                                          |                                       */
    /* data sd1.master;                    |                                          |                                       */
    /*  input Black Blue                   |                                          |                                       */
    /*   Brown Gray Green Orange;          |                                          |                                       */
    /* cards4;                             |                                          |                                       */
    /* 10 20 30 40 50 60                   |                                          |                                       */
    /* 11 22 33 44 55 66                   |                                          |                                       */
    /* ;;;;                                |                                          |                                       */
    /* run;quit;                           |                                          |                                       */
    /**************************************************************************************************************************/

    /*        _       _           _
     _ __ ___| | __ _| |_ ___  __| |  _ __ ___ _ __   ___  ___
    | `__/ _ \ |/ _` | __/ _ \/ _` | | `__/ _ \ `_ \ / _ \/ __|
    | | |  __/ | (_| | ||  __/ (_| | | | |  __/ |_) | (_) \__ \
    |_|  \___|_|\__,_|\__\___|\__,_| |_|  \___| .__/ \___/|___/
                                              |_|
    */

    https://github.com/rogerjdeangelis/utl-create-a-macro-array-from-a-list-with-problematic-delimiters
    https://github.com/rogerjdeangelis/utl-generating-repetitive-code-without-creating-a-macro-array-do-over
    https://github.com/rogerjdeangelis/utl-macro-array-lookups-and-lenght-truncation
    https://github.com/rogerjdeangelis/utl-simple-lookup-code-decode-using-macro-array-format
    https://github.com/rogerjdeangelis/utl-systematically-renaming-and-labeling-over-one-hundred-columns-using-macro-arrays
    https://github.com/rogerjdeangelis/utl-using-macro-arrays-to-simplify-sql-processing
    https://github.com/rogerjdeangelis/utl-array-and-do-over-macros-to-generate-define-statements-of-proc-report
    https://github.com/rogerjdeangelis/utl-dosubl-and-do-over-as-alternatives-to-explicit-macros
    https://github.com/rogerjdeangelis/utl-reduce-list-processing-using-arrays-and-do-over-macros
    https://github.com/rogerjdeangelis/utl-rename-and-cast-char-to-numeric-using-do-over-arrays-in-natve-and-mysql-wps-r-python
    https://github.com/rogerjdeangelis/utl-sampling-data-for-fast-processing-do-over-teradata-exadata-like
    https://github.com/rogerjdeangelis/utl-selecting-all-columns-with-the-same-prefix-using-sql-do-over
    https://github.com/rogerjdeangelis/utl-simplifying-complex-filtering-using-macro-arrays-do-over
    https://github.com/rogerjdeangelis/utl-using-meta-data-to-create-customized-sas-tables-do-over
    https://github.com/rogerjdeangelis/utl_using_sql_arrays_to_avoid_a_long_select_clause
    https://github.com/rogerjdeangelis/utl-complex-join-of-seven-tables-left-self-join-using-sql-arrays
    https://github.com/rogerjdeangelis/utl-computing-counts-using-sql-arrays
    https://github.com/rogerjdeangelis/utl-computing-maxs-and-mins-of-all-numeric-and-character-variables-using-sql-arrays
    https://github.com/rogerjdeangelis/utl-pivot-long-pivot-wide-transpose-partitioning-sql-arrays-wps-r-python
    https://github.com/rogerjdeangelis/utl-simple-example-of-sql-array
    https://github.com/rogerjdeangelis/utl-simplifying-repetitive-code-using-sql-arrays-and-Barts-array-macro
    https://github.com/rogerjdeangelis/utl-sql-arrays-for-very-fast-in-database-processing
    https://github.com/rogerjdeangelis/utl-stack-columns-and-count-values-using-with-and-without-sql-arrays-in-sas-r-and-python
    https://github.com/rogerjdeangelis/utl-transpose-pivot-wide-to-long-using-sql-arrays-in-sas-r-and-python
    https://github.com/rogerjdeangelis/utl-transposing-and-summarizing-by-group-using-sql-arrays
    https://github.com/rogerjdeangelis/utl-transposing-multiple-variables-using-transpose-macro-sql-arrays-proc-report
    https://github.com/rogerjdeangelis/utl-transposing-pivoting-minimums-using-sql-arrays
    https://github.com/rogerjdeangelis/utl-using-sql-arrays-and-do_over-to-cast_0_1-to-Y-N
    https://github.com/rogerjdeangelis/utl-using-sql-arrays-substract-the-values-in-row2-row4-from-row1-by-column
    https://github.com/rogerjdeangelis/utl-using-sql-arrays-to-implement-datastep-variable-ranges
    https://github.com/rogerjdeangelis/utl-very-fast-processing-using-sql-arrays-on-large-core-systems
    https://github.com/rogerjdeangelis/utl_operating_on_macro_arrays

    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
