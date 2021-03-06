# fast-backporter

Bash Script for fast backporting a commit to multiple branches and pushing them to upstream automatically.

Format:

    fast-backporter commit-id branch1 branch2 ... branchn 

Example:

    fast-backporter 36c7cef5e1a90895 rc/sprint-61 rc/sprint-72 rc/sprint-78

Target Branches must have upstream attached or procedure will fail.

The target branches can be stored in an ENV variable using ~/.profile or ~/.bashrc, like:

    LIVE_BRANCHES="rc/sprint-61 rc/sprint-72 rc/sprint-81"

And then can be specified to the backporter command:

    fast-backporter 36c7cef5e1a90895 $LIVE_BRANCHES


Notes:

- To use the script, clone this repo using:

        git clone https://github.com/SoniCoder/fast-backporter

    And then simply include the PATH in your ~/.bash_profile or ~/.bash_rc
- The script aborts whenever it encounters any error like merge-conflict / pull failure / push failure
