# Tools to support the development of [rSFSW2](https://github.com/DrylandEcology/rSFSW2)


## Test Projects
Complete rSFSW2 projects configured to test different functionality. Code is available to
execute these test projects and compare against reference databases.

1. Required setup
    - Folder structure of git clones with adequate branches checked out for
        - ./rSFSW2_tools
    - If needed adjust `dir.external`, i.e., path to external datasets in p1 of test projects

2. Run test projects
    * __Non-interactive__ use
        -
                cd rSFSW2_tools/
                ./Test_projects/Run_all_test_projects.R --help

        - Examples
            - Run test project 4 and clean up
                    `./Test_projects/Run_all_test_projects.R -t=4 -D`
            - Run test project 5, update reference database and clean up if successful
                    `./Test_projects/Run_all_test_projects.R -t=5 -r -d`
            - Clean up `./Test_projects/Run_all_test_projects.R -t=0`

    * __Interactive__ use

        - Start R

        -
                setwd("rSFSW2_tools/") # Set working directory
                source("Test_projects/Run_all_test_projects.R")

        - If the folder 'Test_projects' is not on the current path, then enter on the command prompt

                Enter path to folder of test projects 'Test_projects':

        - Provide details on your test request

                Should the test output be used as future reference (y/n):
                Should the test output be force deleted (y/n):
                Should the test output be deleted (y/n):
                Available tests:
                    1) Test1_downscaling_overhaul
                    2) Test2_LookupWeatherFolders
                    3) Test3_OnlyMeanDailyOutput
                    4) Test4_AllOverallAggregations_snow
                    5) Test5_AllOverallAggregations_mpi
                    6) Test6_wgen_downscaling
                    ...
                Which of the 6 tests should be run ('all'; a single number; several numbers separated by commas; zero or a negative number to delete any temporary objects):


3. Check the outcomes
    - If the output does not compare favorably with the reference database, then a
      problem report is generated.
    - The results of each test project run are summarized by a logical table with
      the columns "has_run", "has_problems", "made_new_refs", "deleted_output", and
      "referenceDB"


## Feedback
Please, report [issues](https://github.com/DrylandEcology/rSFSW2_tools/issues) and
offer [pull-request](https://github.com/DrylandEcology/rSFSW2_tools/pulls)
