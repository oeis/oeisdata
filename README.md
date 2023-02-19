# The Online Encyclopedia of Integer Sequences

This repository holds a Git-formatted export of the content of
the [Online Encyclopedia of Integer Sequences](https://oeis.org/).

Note that this repository does not accept pull requests.
To suggest changes to the OEIS, use the [OEIS web site](https://oeis.org/).

The export in this repository was created at the time recorded in `time.txt`.

## License

The OEIS is copyrighted by the [OEIS Foundation](https://oeisf.org/)
and made available under the terms of the
[Creative Commons Attribution Share Alike 4.0 license](https://creativecommons.org/licenses/by-sa/4.0/).

## Sequence Data

The main OEIS entries are in the `seq` subdirectory.
The entry for A123456 is stored in `seq/A123/A123456.seq`;
the extra layer of subdirectories allows for more efficient manipulation by Git and some file systems.

Each `*.seq` file records the sequence entry in the
[OEIS internal format](https://oeis.org/eishelp1.html).

## Supporting Files

A sequence in the database may have supporting files
linked from the sequence entry's `%H` lines;
these are recorded in the  `files` subdirectory tree.
Each file has a name beginning with the sequence number,
possibly with the leading A changed to a or b.
For example, A000003 has a supporting file `b000003.txt`
stored in `files/A000/b000003.txt`.

This Git repository only holds metadata about supporting files.
The actual content is maintained in [Git LFS](https://git-lfs.com/).
and the repository is configured not to fetch all Git LFS data
by default during `git clone`.

To use Git LFS, you need to download and install it.
See the [Git LFS home page](https://git-lfs.com/) for details.
Then run

	git lfs install

To fetch a specific supporting file, use:

	git lfs fetch -X= -I=files/A000/b000003.txt
	git lfs checkout files/A000/b000003.txt

To fetch all supporting files (many gigabytes), use:

	git lfs fetch -X=
	git lfs checkout
