# Automatic Topological Field Identification in (Historical) German Texts


## HIPKON POS to STTS mapping

The following mapping rules are used to derive STTS tags (Schiller et al., 1999) from the customized POS tagset of the HIPKON corpus. 

**POS**	| **STTS**
----|---------
$_	| $. $, $(
ADJ	|	ADJA
ADJD	|	ADJD
ADJO	|	ADJA
ADJOD	|	CARD
ADJOS	|	NN
ADJS	|	ADJA
ADV	|	ADV
ADVNEG	|	ADV
ADVREL	|	ADV
APPO	|	APPO
APPR	|	APPR
APPRART	|	APPRART
APZR	|	APZR
AVD	|	ADV
CARD	|	CARD
CARDD	|	CARD
DD	|	PDAT
DDA	|	ART
DDREL	|	PRELS
DDS	|	PDS
DDSREL	|	PRELS
DI	|	PIAT
DIA	|	ART
DINEG	|	PIAT
DIS	|	PIS
DPOS	|	PPOSAT
DPOSS	|	PPOSS
FM	|	FM
ITJ	|	ITJ
KOKOM	|	KOKOM
KON	|	KON
KOUS	|	KOUS
NA	|	NN
NE	|	NE
PAV	|	PAV
PAVREL	|	ADV
PI	|	PIS
PINEG	|	PIS
PPER	|	PPER
PRF	|	PRF
PTKA	|	PTKA
PTKNEG	|	PTKNEG
PTKREL	|	ADV
PTKVZ	|	PTKVZ
PTKZU	|	PTKZU
PW	|	PWS
PWAV	|	PWAV
PWAVREL	|	PWAV
PWREL	|	PRELS
ſ	|	$. $,
VAFIN	|	VAFIN
VAINF	|	VAINF
VAPP	|	VAPP
VMFIN	|	VMFIN
VMIMP	|	VMIMP
VMINF	|	VMINF
VN	|	VVPP
VVFIN	|	VVFIN
VVIMP	|	VVIMP
VVINF	|	VVINF
VVPP	|	VVPP
VVPPA	|	ADJA
VVPS	|	VVPP
VVPSD	|	ADJD
VVPSS	|	NN

For punctuation symbols ($\_), the appropriate STTS tag $., $, or $( is determined based on the surface form of the token. In all other cases, the replacement is independent of the particular words and contexts. There is no original POS annotation available for 36 tokens from 3 sentences, hence, the correct STTS tags for these tokens were added manually.

## Training Data Preparation

The Berkeley parser (Petrov et al., 2006) requires the training data to be in a standard treebank format, which is not fulfilled by the topological field data, when the POS tags are taken as input text and word forms are removed. Therefore, the Tüba-D/Z training data in the paper is automatically modified to match the input format of the parser. For example:

*Freudenthal wollte gestern nichts dazu sagen, ob bei ihren Prüfungen ihr etwas aufgefallen sei.*

`Freudenthal did not want to say anything yesterday about whether she had noticed anything during her examinations.'

*Original:*
```
(VF NE)
(LK VMFIN)
(MF ADV PIS PAV)
(VC VVINF)
COMMA
(NF
  (C KOUS)
  (MF APPR PPOSAT NN PPER PIS)
  (VC VVPP VAFIN))
PUNCT
```

*Modified:*
```
(S
  (VF (OTH NE))
  (LK VMFIN)
  (MF (OTH ADV) (OTH PIS) (OTH PAV))
  (VC VVINF)
  (OTH COMMA)
  (NF
    (C KOUS)
    (MF
       (OTH APPR)
       (OTH PPOSAT)
       (OTH NN)
       (OTH PPER)
       (OTH PIS))
    (VC (VC VVPP) (VC VAFIN)))
  (OTH PUNCT))
```

At the top of the tree, a sentence node S is added, which also spans over non-annotated tokens like punctuation or fragments. In addition, intermediate pre-terminal nodes are inserted to ensure that each pre-terminal corresponds to exactly one terminal symbol as it would be the case with word forms and POS tags in a standard syntax tree. While for sentence brackets the bracket label (here: LK, C or VC) is repeated if necessary, for the other fields the artificial label OTH is introduced. Since originally most topological fields do not exhibit any internal structure, the insertion of intermediate nodes, as a side effect, reduces the amount of rules the parser has to learn, which could improve grammar coverage as observed by Becker and Frank (2002).

## DTA Example

Example sentence from the Early New High German theological text *Pia Desideria* by Philipp Jacob Spener from 1676 with topological field annotations:

![Complex DTA Example Sentence](/img/DTA_sent.png)

*`So it is the question whether it would not be adequate at this time that - in absence of that meeting - Christian preachers themselves faithfully reflect on these important things and about what would be beneficial to the Church of God by writing to each other as well as through public printing, so that these thoughts become known to those who are concerned.'*

## DTA Development over Time

Evaluation results for the different genres in the DTA sample over time:

![Evaluation results for the DTA over time](/img/dta_fscore_time.png)
