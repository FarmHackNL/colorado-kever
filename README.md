# colorado-kever
Sterenborg: automatic detection of Colorado potato beetle through image recognition
Team members: Jaap van Loosdrecht

# Werkwijze

- Foto’s zijn gemaakt met DJI Phantom die aanwezig was, ik weet niet met wat voor een camera. De piloot gaf aan dat hij op ca 2m hoogte gevlogen had.
- Algoritme (zie foto hieronder met het gebruikte script):
- Inlezen van het plaatje
- Colorspace omzetten van RGB naar HSV: Hue (kleur), Saturation (verzadiging), Value (helderheid)
- Mbv ThresholdTool zijn de HSV waarden van de kevers ingeleerd. Dit duurde ca 5 minuten, ik heb hier hulp bij gehad van iemand (naam onbekend) die niet, zoals ik,  kleurenblind is.
- Mbv ThresholdHSVChannels kan het plaatje gesegmenteerd worden, dit levert een binair plaat je op met pixels met de waarde 1 waar de kevers zitten en met de waarde 0 voor de achtergrond.
- Na analyse bleek dat deze HSV waarden ook in de punten van de bladeren voorkomt. Omdat maar kleine gebieden zijn kunnen deze gemakkelijk weg gefilterd worden met de RemoveBlobs operator die objecten kleiner dan 10 pixels verwijdert.
- De rest van de regels in het script zijn om de cirkel rond de kevers te tekenen.

# Opmerkingen

- Deze oplossing is het resultaat van een half uur werk en zeker nog niet robuust voor een echte oplossing. In de “paden” die tussen de planten zitten bv ook delen met de dezelfde HSV waarden. Verder onderzoek is nodig om die er uit te filteren, bv op basis van bv grootte, vorm en of object in een groene omgeving (blad) ligt. Een totaal andere aanpak is om met andere (complexere) patroonherkenningstechnieken de beelden te analyseren. Hiervoor zal nog flink wat werk moeten verricht. Met name het goed robuust maken voor veranderde belichtingsomstandigheden oa intensiteit en witbalans. 


# Uitvoeren

- Het script (script.jls) en de test foto (coloradokever_rgb.jl) van de screenshot. Een demo versie van de gebruikte Computer Vision ontwikkelomgeving (VisionLab) kun je downloaden van www.vdlmv.nl/download. Indien je wilt kun je hier mee verder experimenteren. Op www.nhlcomputervision.nl/courses staat een cursus Computer Vision waar dit softwarepakket wordt gebruikt.

Een presentatie die vrijdagmorgen bij van Hall Larenstein gaf, hierin oa enkele dia’s mbt tot ons experiment om Altenaria te kunnen onderscheiden van ozonschade op aardappelplanten mbv hyperspectrale camera’s.

