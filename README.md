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
