# Super Mario Odyssey save-file CRC32

This repository documents the checksum stored at the beginning of
Super Mario Odyssey save files on Nintendo Switch.

## Discovery

The four bytes at offset `0x00` contain the standard CRC32 checksum of
all file data beginning at offset `0x04` and continuing to the end of
the file.

The CRC32 value is stored in little-endian byte order.

## Verification procedure

1. Read the first four bytes of the save file.
2. Calculate the CRC32 of the file from offset `0x04` to the end.
3. Convert the calculated CRC32 to little-endian byte order.
4. Compare the result with the first four bytes.

This relationship was verified locally using five different save files.

## Privacy

The original save files are not published because they may contain
personal or account-related information.
