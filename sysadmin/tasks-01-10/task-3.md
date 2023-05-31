## Task 3

It was pointed out that the application servers (`stapp01`, `stapp02` and `stapp03`) have incorrect timezones, which should be `Asia/Kuala_Lumpur`.

This mismatch can be accomplished with the command `sudo timedatectl set-timezone Asia/Kuala_Lumpur` in each server. See how it can be done for the `stapp01` server below:

<img width="378" alt="image" src="https://github.com/kmilach/kodekloud-engineer/assets/53876300/aafa9342-3318-44e3-897e-756d05e3b2a3">
