# odp_to_beamer
- I created a new Overleaf project and uploaded all the files there.

- I manually wrote the 14_time_distribution_sliced.tex file while referring to 08_rest.tex because the content was less.

- If there was more content, I could unzip the .odp file (14_time_distribution_sliced.odp) and extract the text from content.xml using VSCode XML tools to create an XML tree for better visualization.

- Some thoughts – 14_time_distribution_sliced.tex renders perfectly with all the images and graphs, but the 14_time_distribution_sliced_lecture.pdf and 14_time_distribution_sliced_handout.pdf files are missing these figures.

- I suspect this is because of the @tail -n +4 $(MASTER).tex > temp.tex line in the Makefile for lecture and handout.

- Another thing, I had to manually run make handout to generate the handout PDF. I could not troubleshoot why make fulda did not generate the handout material.
