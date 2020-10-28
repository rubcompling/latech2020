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

## DTA Example

Example sentence from the Early New High German theological text *Pia Desideria* by Philipp Jacob Spener from 1676 with topological field annotations:

![Complex DTA Example Sentence](/img/DTA_sent.png)

*`So it is the question whether it would not be adequate at this time that - in absence of that meeting - Christian preachers themselves faithfully reflect on these important things and about what would be beneficial to the Church of God by writing to each other as well as through public printing, so that these thoughts become known to those who are concerned.'*

## DTA Development over Time

Evaluation results for the different genres in the DTA sample over time:

![Evaluation results for the DTA over time](/img/dta_fscore_time.png)
