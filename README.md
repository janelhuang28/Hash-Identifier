# Hash-Identifier
This page documents how to use Hash Identifier to identify the hash types that have been used for hashes

## Prerequisites

1. Download Hashcat using `` sudo apt install hashcat``
2. Download Hash Identifier ``git clone https://github.com/blackploit/hash-identifier.git ``

Finding the hashes for the following 
Hash 1: 7196759210defdc0
Hash 2: 1bbb234c81ef04a1c2f441253952a556276669d7fc9d1ee765bd4b18f796699d (256)
Hash 3: 32c0ced56f1fe08583bdb079d85a35a81995018c (1)
Hash 4: 753b27807b690ef889a259f3b219e024bf5c6c33c8d56116943d9285a0b55b2050981f29e6fafa660428c48d7db3c4bd2e8dd48f87c8e90bde5e0c82ed23be10 (512)
Hash 5: 5f804b61f8dcf70044ad8c1385e946a8 (md5)

## To use

1. Run Hash Identifier using the following command ``python3 hash-id.py ``
2. Pastes the hashes into ``Hash:``
Example:
![image](https://user-images.githubusercontent.com/39514108/151734500-4d279293-2fcb-424c-9d65-75af61be2738.png)
3. From ![image](https://user-images.githubusercontent.com/39514108/151734696-c52ea983-5578-46ca-b9e0-86db7e578c62.png)
 (https://hashcat.net/wiki/doku.php?id=example_hashes), we can decrypt Hash 1 using SQL323 as it's length is the most similar for SQL hashes.
4. Now after creating a file with the word ``hashcat`` in it and running the command ``sudo hashcat -m 200 -a 0 7196759210defdc0 example.dict --force`` which uses
* -m - mode of the hash type
* -a - attack mode, 0 for straight
* --force - ignore warnings
5. Now we can see that the hash translates to hashcat: ![image](https://user-images.githubusercontent.com/39514108/151735080-c08cc9fa-7ad7-4ac4-ba7b-bb8323a401ec.png)
