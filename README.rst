slm_usage
=========

Collect and Report SLURM usage. (This application is not ready yet.)

Commands
------------------


``slm_usage trim_log`` - Trims log file::

    slm_usage trim_log --import /var/log/slurm/accounting \
                       --export /var/log/slurm/accounting-2016-02 \
                       --start 2016-02-01 \
                       --end 2016-02-29

What this command does is;

#. import the slurm accounting log file ``/var/log/slurm/accounting``.
#. read each line
#. convert the unix time to the date and check if it's between 2016-02-01 and 2016-02-29.
#. If it's in, check if the account is ``(null)``, and replace it to user's group name.
#. Export the result to ``/var/log/slurm/accounting-2016-02``.


``slm_usage update_cpu_hours`` - Update cpu_hours::

    slm_usage update_cpu_hours --tinydb-file /path/to/tinydb \
                               --import /var/log/slurm/accounting-2016-02
