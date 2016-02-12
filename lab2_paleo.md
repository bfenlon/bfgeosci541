#Lab Exercise 2

> The html actually made it a bit difficult to grade, maybe just stick to native GitHub flavoured markdown. Good lab though, 18.3/20.

##Part 1 questions
<ol>
<li><p>Following are my initial and final classifications. Without looking at the data I did the initial classification based solely on what I thought was relavent (visually) to distinguish among species. My specific reasoning is explained for each species with the 'Distinguishing characteristics' tag. For the final classifications the choice of relative stratigraphic position cutoffs was arbitrary, and was in no way influenced by a logical system. Herein lies the flaw of this classification, because even if there is quantifiable data to work with and subset, the parameter selections are prone to human error/bias. The result was that, with quantitative data to work with, my classifications necessarily became more broad to account for the new (as opposed to the initial classification) data.</p>

<h3>Initial classifications (visual traits only)</h3>
<ul>	
	<li>Species 1<br />
	Distinguishing characteristics: deep shell pattern, more repetetitions and shallower than species 3<br />
	1,2,4,8,20</li>

	<li>Species 2<br />
	Distinguishing characteristics: mostly smooth shell with hints of shallow striations<br />
	3,9,10,13,15,24,25</li>

	<li>Species 3<br />
	Distinguishing characteristics: smooth, deep pattern visible in side view<br />
	6,12,18,21</li>

	<li>Species 4<br />
	Distinguishing characteristics: U/D looks (visually) to be quite low<br />
	5,14,17,19,23</li>

	<li>Species 5<br />
	Distinguishing characteristics: wavy pattern present in shell<br />
	7,11,16,22</li>
</ul>
<h3>Secondary classifications (visual and quantitative traits)</h3>
<ul>
	<li>Species 1<br />
	Distinguishing characteristics: intermediate -> deep ribbing regardless of size, relative stratigraphic 
	position is greater than 8<br />
	1,4,8,11,20,21</li>

	<li>Species 2<br />
	Distinguishing characteristics: deep ribbing in small specimens, smoother in the larger ones (could 
	represent ontogenetic growth due to various stages of ribbing), relative stratigraphic position between 
	9.1 and 6.8<br />
	2,6,7,9,10,17,25</li>

	<li>Species 3<br />
	Distinguishing characteristics: sexual dimorphism present, both smooth and ribbed specimens, UD within 
	.05 of .4, relative stratigraphic position between 5.1 and 3.7<br />
	3,12,15,18,22,24</li>

	<li>Species 4<br />
	Distinguishing characteristics: relative stratigraphic position less than 4.7, deviation from mean of 
	ratio for umbilical to width is on average negative<br />
	5,13,14,16,19,23</li>

</ul>

</li>

<p><li>Morphologically I found the patterns present to be both relavent and misleading at the same time. On one hand they may represent differences in phylogeny and therefore lead to the assumption of two different species being present. On the other hand, however, the two different forms could represent two different sexes or two different points in ontogeny of the same species.</li></p>

<p><li>The ontogenetic change that I hypothesized in species 2 showed deeper ribs in smaller specimens and flattened out through the lifetime.</li></p>

<p><li>Evaluating possible sexual dimorphism was somewhat difficult, because while the fossil record is good for many things, sexing ammonites is not among its specialties. I do not have the wherewithal to determine possible sexual dimorphism, but that does not disprove its presence in this small sample.</li></p>
</ol>

> -2 points. Females tend to be larger than males, it was in the supplementary readings. Similarly, the chambers tend to be more widely spaced in juveniles than adults.

##Part 2 questions
###Section 1
1. land, links, species, site, and outline
2. land is an array, links and outline are matrices, species and site are factors
3. 12x2x40

###Section 2
1. land
2. ProcrustesHummingbirds <- gpagen(hummingbirds[["land"]])
3. plotTangentSpace(ProcrustesHummingbirds[["coords"]], warpgrids=FALSE, verbose=FALSE)
4. Qualitatively looking at the resulting PCA graph, there is no singular species of hummingbird. When changing ProcD to FALSE in the gpagen function, which slides the semilandmarks based on minimizing bending energy (removes artifacts due to equidistant semilandmark analysis; considered to be more accurate), two distinct groupings form. One has a majority of the points, while the other contains only three of the points.

##Part 3 questions
###Section 1
1. Fangs longer than 6 inches is the synapomorphy of the clade containing D and E.
2. Sulfurous odor would be a plesiomorphic character of that clade.
3. Adorable eyelashes is the synapomorphy for the clade containing A and B.
4. C, D, and E all have sulfurous odor. 
5. Laser death rays distinguish E from D. E is probably going to win in the long run when looking at niche conservatism above the species level. 
6. Adorable eyelashes, being present in A and B's most recent common ancestor, is a synapomorphy. 
7. Family 1 is monophyletic, family 2 is polyphyletic, and family 3 is monophyletic.
###Section 2
1. As to whether it is advisable I am not certain, but it would make more sense to be grouped with B and C than with D and E. Although this would be paraphyletic by excluding D and E, it would be more appropriate than grouping A with only D and E.
2. Group 1 is paraphyletic, group 2 is monophyletic, group 3 is paraphyletic, group 4 is monophyletic, and group 5 is polyphyletic. 

##Part 4 questions
1. Paedomorphosis, retention of juvenile characteristics.
2. Gryphaea gigantea
3. Because Olenellus armatus most closely resembles the juvenile form of Olenellus lapworthi, paedomorphosis is present in the Olenellus example.
