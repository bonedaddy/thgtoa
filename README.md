Welcome.

This is a maintained technical guide that aims to provide introduction to various online tracking techniques, online id verification techniques and guidance to creating and maintaining (truly) anonymous online identities including social media accounts safely and legally. No pre-requisites besides English reading are required. **It is written with hope for activists, journalists, scientists, lawyers, whistle-blowers, and good people being oppressed/censored anywhere!**

This guide is an open-source non-profit initiative, [licensed] <sup>[[Mirror]][8]</sup> <sup>[[Archive.org]][9]</sup> under Creative Commons Attribution 4.0 International ([cc-by-4.0]) and is not sponsored/endorsed by any commercial/governmental entity. This means that you are free to use my guide for pretty much any purpose including commercially as long as you do attribute it.

The latest version is **0.9.7b**, See the CHANGELOG at <https://anonymousplanet.org/CHANGELOG.html> <sup>[[Mirror]][10]</sup> <sup>[[Tor Mirror]][15]</sup>

Latest Online HTML versions at:
- Main: <https://anonymousplanet.org/guide.html> <sup>[[Archive.org]][6]</sup> <sup>[[Archive.today]][7]</sup> 
- Mirror: <https://mirror.anonymousplanet.org/guide.html> <sup>[[Archive.org]][5]</sup> <sup>[[Archive.today]][19]</sup> 
- Tor Mirror: <http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/guide.html> 
- Archive.today over Tor: <http://archivecaslytosk.onion/anonymousplanet.org/guide.html>

Latests PDF versions at:
- Light Theme: <https://anonymousplanet.org/guide.pdf> <sup>[[Mirror]][1]</sup> <sup>[[Archive.org]][2]</sup> 
- Light Theme over Tor: <http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/guide.pdf> 
- Dark Theme: <https://anonymousplanet.org/guide-dark.pdf> <sup>[[Mirror]][3]</sup> <sup>[[Archive.org]][4]</sup> 
- Dark Theme over Tor: <http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/guide-dark.pdf>
- All latest PDFs are also available on CryptPad at <https://cryptpad.fr/drive/#/2/drive/view/Ughm9CjQJCwB8BIppdtvj5zy4PyE-8Gxn11x9zaqJLI/>

The PDF files in this guide have been checked by VirusTotal and Hybrid-Analysis, see the links below (**Note that this guide does not endorse VirusTotal/Hybrid-Analysis. Those should be used with extreme caution and never with any sensitive files due to their privacy policies.**)
- Light Theme: [[VirusTotal]][light_virustotal], [[Hybrid-Analysis]][light_hybrid_analysis]
- Dark Theme: [[VirusTotal]][dark_virustotal], [[Hybrid-Analysis]][dark_hybrid_analysis]

For additional safety; you can always double check them using PDFID which you can download at <https://blog.didierstevens.com/programs/pdf-tools/> (You might be wondering why should trust a random python script? Well it's open-source and well-known. It's probably a safer bet than trusting a random PDF).

Here are the steps:

- Install latest 3.9.x version of Python on your OS, Download PDFID and, from a command prompt or terminal, run:

```python pdfid.py file-to-check.pdf```

And you should see the following entries at 0 for safety, this 0 means there is no Javascript or any action that could possibly embed malicious scripts. Normally this won't be neceessary as most modern PDF readers won't execute those scripts anyway.

```
/JS                    0 #This indicates the presence of Javascript which could be malicious
/JavaScript            0 #This indicates the presence of Javascript which could be malicious
/AA                    0 #This indicates the presence of automatic action on opening
/OpenAction            0 #This indicates the presence of automatic action on opening
/AcroForm              0 #This indicates the presence of AcroForm which could contain malicious JavaScript
/JBIG2Decode           0 #This indicates the PDF uses JBIG2 compression which could be used for obfuscating malicious content
/RichMedia             0 #This indicates the presence rich media within the PDF such as Flash
/Launch                0 #This counts the launch actions
/EmbeddedFile          0 #This indicates there are embedded files within the PDF
/XFA                   0 #This indicates the presence of XML Forms within the PDF
```

All the files in this guide are also cryptographically signed using GPG and their integrity can be verified with the published SHA256 Chrecksum Hashes on this website.

SHA256 Checksums of all the PDFs are available here: 
- Main and Mirror: <https://anonymousplanet.org/sha256sum.txt> <sup>[[Mirror]][11]</sup>
- Tor Mirror: <http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/sha256sum.txt>

SHA256 Checksums and GPG keys of the full repository releases files are available within the checksum file at <https://github.com/AnonymousPlanet/thgtoa/releases/latest>

The GPG signatures for each PDF file are available here:
- (Light) Main and Mirror: <https://anonymousplanet.org/guide.pdf.asc> <sup>[[Mirror]][17]</sup>
- (Light) Tor Mirror: <http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/guide.pdf.asc>
- (Dark) Main and Mirror: <https://anonymousplanet.org/guide-dark.pdf.asc>  <sup>[[Mirror]][18]</sup>
- (Dark) Tor Mirror: <http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/guide-dark.pdf.asc>

Now to check the integrity of the files using the SHA256 Checksums please do the following:

Windows:
- From a command prompt, run ```certutil -hashfile filename.txt sha256```
- Compare the result with the hash in the online checksum files. They should match.

MacOS:
- From a terminal, run ```shasum -a 256 /full/path/to/your/file```
- Compare the result with the hash in the online checksum files. They should match.

Linux: 
- From a terminal, run ```sha256sum /full/path/to/your/file```
- Compare the result with the hash in the online checksum files. They should match.

All commits and releases on this repository are cryptographically signed and verified using the same GPG key. Check for the "Verified" tags on each commit or release.

Now to verify the files with GPG signatures, you should first install gpg on your system:
- Windows: Install gpg4win from <https://www.gpg4win.org/download.html>
- MacOS: Install GPG Tools from <https://gpgtools.org/>
- Linux: gpg should be installed by default

Import the GPG key using the following command from a command prompt or terminal:

```gpg --auto-key-locate nodefault,wkd --locate-keys 0xEB16B6AB4AB7BA61F33E2DFD0051E9A589DAB601```

In theory this command should fetch the key from the a default pool server. If this doesn't work, you can also download/view it directly from here: <https://anonymousplanet.org/AnonymousPlanet_0x89DAB601_public.asc> <sup>[[Mirror]][12]</sup> <sup>[[Tor Mirror]][14]</sup>

For redundancy, you can also verify the authenticity of this GPG signature using:
- My Keybase.io profile <https://keybase.io/anonymousplanet>
- My Keyoxide.org profile <https://keyoxide.org/eb16b6ab4ab7ba61f33e2dfd0051e9a589dab601>

As well as the published key on (search for the fingerprint ```0xEB16B6AB4AB7BA61F33E2DFD0051E9A589DAB601```):
- <https://pgp.mit.edu>
- <https://keys.openpgp.org>
- <https://keyserver.ubuntu.com> 

You should then import it manually by issuing the following command on any OS:

```gpg --import AnonymousPlanet_0x89DAB601_public.asc```

Finally, verify the asc signature file (links above) against the PDF files by issuing the following commands: 

```gpg --verify guide.pdf.asc guide.pdf"```
```gpg --verify guide-dark.pdf.asc guide-dark.pdf"```

This should output a result showing it matches and it's ok.

Feel free to submit issues using Github Issues.

If you'd like to make a donation to this project, you can do so from <https://anonymousplanet.org/donations.html> <sup>[[Mirror]][13]</sup> <sup>[[Tor Mirror]][16]</sup>.
All the donations will be strictly used within the context of this project. All donations are logged on the Donate page (inboound and spendings). 

Follow or contact me on: 
- Twitter: <https://twitter.com/AnonyPla>
- Mastodon: <https://mastodon.online/@anonypla>
- Element/Matrix.org: ```@anonypla:privacytools.io```
- Reddit: <https://old.reddit.com/message/compose/?to=AnonyPla>
- E-Mail: <contact@anonymousplanet.org>

Discussion Channels (**be careful as none of those are actively moderated, or encrypted**):
- Matrix: ```#online-anonymity:matrix.org```
- Github Discussions: <https://github.com/AnonymousPlanet/thgtoa/discussions>

Criticism, opinions, ideas are welcome! The ultimate intent is to not have any inaccuracies in the guide.

Have a good read and feel free to share/recommend it!

[cc-by-4.0]: https://creativecommons.org/licenses/by/4.0/
[licensed]: https://anonymousplanet.org/LICENSE.html
[light_virustotal]: https://www.virustotal.com/gui/file/2aee47c5b35fd595c87d163fca4f20e8f49baf4d14adae71827cdb0bd4acaf60/detection
[light_hybrid_analysis]: https://hybrid-analysis.com/sample/2aee47c5b35fd595c87d163fca4f20e8f49baf4d14adae71827cdb0bd4acaf60
[dark_virustotal]: https://www.virustotal.com/gui/file/6551bdb802cbcdfb6a6dc9044e3ef71bae858027e274bdcdcc4cad71b7ff4ccc/detection
[dark_hybrid_analysis]: https://hybrid-analysis.com/sample/6551bdb802cbcdfb6a6dc9044e3ef71bae858027e274bdcdcc4cad71b7ff4ccc
[1]: https://mirror.anonymousplanet.org/guide.pdf 
[2]: https://web.archive.org/web/https://anonymousplanet.org/guide.pdf
[3]: https://mirror.anonymousplanet.org/guide-dark.pdf 
[4]: https://web.archive.org/web/https://anonymousplanet.org/guide-dark.pdf
[5]: https://web.archive.org/web/https://mirror.anonymousplanet.org/guide.html
[6]: https://web.archive.org/web/https://anonymousplanet.org/guide.html
[7]: https://archive.fo/anonymousplanet.org/guide.html
[8]: https://mirror.anonymousplanet.org/LICENSE.html
[9]: https://web.archive.org/web/https://anonymousplanet.org/LICENSE.html
[10]: https://mirror.anonymousplanet.org/CHANGELOG.html
[11]: https://mirror.anonymousplanet.org/sha256sum.txt
[12]: https://mirror.anonymousplanet.org/AnonymousPlanet_0x89DAB601_public.asc
[13]: https://mirror.anonymousplanet.org/donations.html
[14]: http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/AnonymousPlanet_0x89DAB601_public.asc
[15]: http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/CHANGELOG.html
[16]: http://thgtoa7imksbg7rit4grgijl2ef6kc7b56bp56pmtta4g354lydlzkqd.onion/donations.html
[17]: https://mirror.anonymousplanet.org/guide.pdf.asc
[18]: https://mirror.anonymousplanet.org/guide-dark.pdf.asc
[19]: https://archive.fo/mirror.anonymousplanet.org/guide.html