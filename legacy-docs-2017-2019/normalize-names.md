# Normalize File and Directory Names

Folder titles and filenames are normalized to remove characters that can cause problems with computer systems and processes. For example, if a filename contains a forward slash (/), it will not write correctly to tape. This should be done to all accessions, even if there is not a deed of gift, to ensure proper preservation of the files.

Permitted characters are letters, numbers, underscores, dashes, periods, and tilde (~). Spaces are replaced with underscores and all other characters are removed. This matches the normalization that is required for files to be saved to the University Libraries' preservation storage.

Normalize folder and file names using a script. The script generates a file called **accession-number_normalized-filenames.txt** that contains both versions of normalized folder and file names to document the changes made. Save this file with the preservation documentation for the accession.

For guidance on how to install the script on a computer, see the instructions below.

## Normalize names for a single accession

The following Perl script is used to normalize folder titles and filenames for a single accession. To install the script on a computer, copy the following script text to a text file and save as **normalize_names_accession** with no file extension to the computer. Change permissions on the file for it to be executable, either through the GUI (in Linux Properties - Permissions - Allow executing file as program) or in the terminal (using the `chmod +x` command).

```Perl
#!/usr/bin/perl

use Cwd 'abs_path';

use 5.010;

my $al = @ARGV;

print "Usage: normalize_names_accession accession_number path/to/data/directory\n" and exit if $al != 2;

my $accession = $ARGV[0];

my $path = abs_path($ARGV[1]);

open OUT, ">/home/digipres/Desktop/$accession\_normalized-filenames.txt";

sub replace_in_dir {

  my $dir = shift;

  my $full_dir = abs_path($dir);

  chdir $full_dir or die "Could not chdir dir $full_dir";

  my @files = <*>;


  for my $file ( @files ){

	next if $file eq '.' or $file eq '..';

	chdir $full_dir;

	my $original = $file;

	$file =~ s/[^a-z0-9_ .~-]//gi;

	$file =~ s/ /_/g;

	#$file = lc $file;

	rename($original,$file) or die "Could not rename file: $!\nOriginal: $original File: $file";

	$full_original = abs_path($original);

	$full_original =~ s/$path\///;

	$full_file = abs_path($file);

	$full_file =~ s/$path\///;

	print OUT "$full_original\t$full_file\n";

	$file = abs_path($file);

	if ( -d $file ){

  	replace_in_dir("$file");

	}

  }

}

replace_in_dir($path);

close OUT;
```

Run the script by typing the path to the script, the accession number, and the path to the accession folder in the terminal. When the script is complete, an **accession-number_normalized-filenames.txt** file will be saved to the desktop.

`$ /home/digipres/scripts/normalize_names_accession accession-number path/to/accession`

## Normalize names for a group of accessions

The following is the Perl script used to normalize folder titles and filenames for a group of accessions at once. To install the script on a computer, copy the following script text to a text file and save as **batch_normalize_names_accession** with no file extension to the computer. Change permissions on the file for it to be executable, either through the GUI (in Linux Properties - Permissions - Allow executing file as program) or in the terminal (using the `chmod +x` command). For this script to work, the **normalize_names_accession** script must also be saved to the computer and all of the accession folders to be normalized need to be located in the same directory.

```Perl
#!/usr/bin/perl

use Cwd 'abs_path';

use 5.010;

my $al = @ARGV;

print "Usage: batch_normalize_names_accession path/to/accession/directory\n" and exit if $al != 1;

my $path = abs_path($ARGV[0]);

chdir $path;

my @files = <*>;

for my $file ( @files ){

  next if $file eq '.' or $file eq '..';

  next unless ( -d $file );

  chdir $path;


  say "Normalizing $file";

  #my $error = `normalize_names $file $file 2>&1`;

  #die "Cannot normalize_names for $file:\n$error" unless $? == 0;

  system("normalize_names_accession $file $file 2>&1") == 0 or die "Cannot normalize_names for $file: $?";

}
```

Run the script by typing the path to the script and the folder that contains the accessions into terminal. When the script is complete, a **accession-number_normalized-filenames.txt** file for each accession will be saved to the desktop.

`$ /home/digipres/scripts/batch_normalize_names_accession path/to/folder/with/accessions`
