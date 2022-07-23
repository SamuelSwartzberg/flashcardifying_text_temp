# indication

⟮File format⟯ and ⟮file type⟯ are ⟮basically synonyms⟯. 
the ⟮file format/type⟯ is ⟮the structure/specification⟯ of what ⟮the binary contents⟯ of ⟮c+;a file following this ⟮s4;file format⟯⟯ ⟮mean/how they should be interpreted⟯. 
There are ⟮three common ways⟯ to specify ⟮a file format⟯: ⟮s8;⟮Filename extensions⟯, ⟮internal metadata⟯, and ⟮external metadata⟯.⟯ 

⟮Windows⟯ and ⟮Mac⟯  use ⟮file extensions⟯ to ⟮identify file type⟯. 
⟮Linux⟯ generally uses ⟮magic numbers⟯ to ⟮identify file type⟯. 
⟮File extensions⟯ can be ⟮useful⟯ on ⟮Linux⟯, but ⟮are generally not necessary⟯. 

Specifying ⟮file format⟯ via ⟮internal metadata⟯ is having some sort of information ⟮as part of the file⟯ that specifies its ⟮format⟯. 
⟮Magic numbers⟯ are a form of ⟮internal metadata⟯. 
⟮magic numbers⟯ are ⟮a byte/series of bytes⟯ (often at ⟮the beginning of the file⟯) that ⟮identify the file format⟯. 

Specifying the ⟮file format⟯ via ⟮filename extensions⟯ involves ⟮suffixing⟯ ⟮the filename⟯ with ⟮a dot⟯ and ⟮some short name⟯. 
many ⟮file extensions⟯ are ⟮three-letter⟯ because ⟮dos did not allow for longer file extensions⟯ 
⟮.htm⟯ is ⟮a synonym for .html⟯ that only exists because ⟮dos required 3 char file extensions⟯ 

Specifying ⟮file format⟯ via ⟮external metadata⟯ is having some sort of information ⟮as part of a message/protocol/file system⟯ that specifies its ⟮format⟯. 

⟮Media type⟯ is a way for ⟮identifying the file format⟯ of a file via ⟮external metadata⟯. 
⟮Media type⟯ is ⟮the most common way⟯ for identifying file format on ⟮the internet⟯. 
⟮Media type⟯ ⟮used to⟯ be called ⟮MIME type⟯. 
⟮Media type⟯ syntax: ⟮‹type›/‹subtype›⟯⟮{+‹suffix›⟯}⟮c+;[;‹parameter›]⟯ ⟮(c:60;‹tree›⟯ left out because not commonly used) 
Common types for media type's ⟮type⟯ are a⟮pplication, audio, video, image, text⟯ 
Common ⟮subtypes⟯ for ⟮the type image⟯ might be ⟮webp, png, svg+xml, jpeg⟯ 
If a file is ⟮XML⟯, its ⟮media type⟯ gets ⟮a suffix of xml (+xml⟯) 
The ⟮HTTP header⟯ for ⟮media type⟯ is ⟮Content-Type⟯. 

A ⟮mailcap⟯ ⟮file⟯ maps ⟮media types⟯ to ⟮applications to view/execute them.⟯ 
⟮Mailcap files⟯ consist of ⟮mappings⟯, with ⟮one⟯ per ⟮line⟯. 
⟮Mailcap mapping⟯ syntax: ⟮‹media-type›⟯⟮c+;;⟯⟮‹program-to-execute›⟯ ⟮%s⟯ 
For ⟮mailcap⟯, ⟮%s⟯ represents ⟮the file of the relevant MIME type⟯ that ⟮the program gets passed⟯ 

## common file extensions

File format|File extension
⟮TypeScript source code⟯|⟮.ts⟯
⟮M3U playlist⟯|⟮.m3u⟯
⟮Tex source document⟯|⟮.tex⟯
⟮WebVTT⟯|⟮.vtt⟯
⟮JS Modules⟯|⟮either .js or .mjs⟯
⟮Markdown source document⟯|⟮.md⟯
⟮YAML source document (common but not advised⟯)|⟮.yml⟯
⟮YAML source document (advised but less common⟯)|⟮.yaml⟯
⟮bzip2 archive⟯|⟮.bz2⟯
⟮class files (latex⟯)|⟮.cls⟯
⟮windows executable⟯|⟮.exe⟯
⟮iCalendar⟯|⟮.ics⟯
⟮ruby source coude⟯|⟮.rb⟯
⟮rust source code⟯|⟮.rs⟯
⟮short for style / but are called packages⟯|⟮.sty⟯
⟮plaintext files (arbitrary⟯)|⟮.txt⟯
⟮vCard⟯|⟮.vcf⟯
⟮Free/busy time (iCalendar⟯)|⟮.ifb (or .ifbf on macOS⟯)
⟮BibTeX source file⟯|⟮.bib⟯
⟮arbitrary binary data⟯|⟮.bin⟯
⟮JSON document⟯|⟮.json⟯
⟮SCSS syntax source file⟯|⟮.scss⟯
⟮sass syntax source file⟯|⟮.sass⟯
⟮XML document⟯|⟮.xml⟯
⟮fountain source document⟯|⟮.fountain⟯
⟮shell script⟯|⟮.sh⟯