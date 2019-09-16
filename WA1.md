*This assignment is to explore a few different tools that can be piped together to reorganize or manipulate the data in your files.
*The data consists of a gene sequence for a variety of different animals.

One thing that someone may want to do is reorder the sequences by sequence length and work with only the 5 shortest sequences and putting them into their own folder.

wc -c | sort -n | head -5 > WA1seq.lengths

Someone may only want to work with sequences that share a certain short sequence within the longer sequence. We would expect to see all of the protein sequences that contain that exact sequence, not just something similar or with parts of our search sequence. It will place these files into a new folder named shared.shortseq.data

grep -w <ILKKKGHHE>* > shared.shortseq.data 

It is also possible that you may want to work only with the sequences that contain a higher concentration of G's or C's. The desired output would be that it finds the occurences of 'G' in a file, counts them, and then sorts them by how many occurences.

grep G -o | wc -c | sort -n
