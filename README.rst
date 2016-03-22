slm_usage
=========

Collect and Report SLURM usage. (This application is not ready yet.)

Necessary features
------------------


Trim log file::

    slm_usage trim-log --import /var/log/slurm/accounting \
                       --export /var/log/slurm/accounting-2016-02 \
                       --start 2016-02-01 \
                       --end 2016-02-29

What this command does is;

#. import the slurm accounting log file ``/var/log/slurm/accounting``.
#. read each line
#. convert the unix time to the date and check if it's between 2016-02-01 and 2016-02-29.
#. If it's in,
   #. If the account is ``(null)``, replace it to user's group name.
#. Export the result to ``/var/log/slurm/accounting-2016-02``.
