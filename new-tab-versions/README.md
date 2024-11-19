Included is a version of flight-401-blr that has modified the supporting C files to include test cases for all the existing protocol cases that currently exist between the original Tab definition and the TAOLST_PROTOCOL cases.

| taolst_protocol.c | tab.c                        | TRANSITIONING | new-tab.c                    |
|-------------------|------------------------------|---------------|------------------------------|
| APP_GET_TELEM     | BOOTLOADER_WRITE_PAGE_ADDR32 | APP_GET_TELEM | BOOTLOADER_ACK               |
| APP_GET_TIME      | COMMON_DEBUG                 | APP_TELEM     | BOOTLOADER_ERASE             |
| APP_REBOOT        | COMMON_DATA                  | APP_REBOOT    | BOOTLOADER_NACK              |
| APP_SET_TIME      |                              |               | BOOTLOADER_PING              |
| APP_TELEM         |                              |               | BOOTLOADER_WRITE_PAGE        |
| COMMON_ASCII      |                              |               | BOOTLOADER_JUMP              |
|                   |                              |               | COMMON_ACK                   |
|                   |                              |               | COMMON_NACK                  |
|                   |                              |               | BOOTLOADER_WRITE_PAGE_ADDR32 |
|                   |                              |               | COMMON_DEBUG                 |
|                   |                              |               | COMMON_DATA                  |
|                   |                              |               | APP_SET_TIME                 |
|                   |                              |               | APP_GET_TIME                 |

NOTE: COMMON_ASCII will not be transitioned into the new-tab because it utilizes the same opcode as COMMON_DEBUG. Future iterations may change the opcodes of one or both of these commands to allow both in one iteration.

Another note: Anything in new-tab.c that was not listed in taolst_protocol.c or tab.c was included in both, and removed from the initial two columns for clarity.
