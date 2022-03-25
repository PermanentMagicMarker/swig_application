
------------------------------------------------------------------------------------------------------
SWIG Database
------------------------------------------------------------------------------------------------------

The SWIG database is prepared in CSV formats containing several datasets. The first dataset, named i_cm.csv, contains cumulative infiltration data in centimetre units. The individual infiltration tests are identified in the i_id column and the related values are stored in the i_values column. The corresponding time intervals in hours for the infiltration data are stored in the t_hour.csv file and can be related using the t_id column, while the values are stored in the t_values column. The constant or varying pressure or tension heads (if any) during infiltration measurements are also reported in another dataset named tension_cm.csv and can be related using the tension_id column, while the values are stored in the tension_values column. The database also contains additional variables and information relevant to the infiltration data provided by data owners or digitized from articles, which is provided in the metadata.csv file and can be related using the metadata_id and metadata_values column. The headers for the metadata_values column are stored in the metadata_headers.csv file.

------------------------------------------------------------------------------------------------------

Since the geometric mean diameter (dg) and standard deviation (Sg) of soil particle sizes are rarely measured, both parameters were computed using the following equations (Shirazi and Boersma, 1984):


		dg = exp(a), a = 0.01*∑fi*lnMi			Equation 1


		Sg= exp(b), b² = 0.01*∑fi*ln²Mi - a²		Equation 2


where fi is the percent of total soil mass having diameters equal to or less than Mi, i corresponds to clay, silt, and sand fractions having the arithmetic mean of two consecutive particle size limits of 0.01, 0.026, and 1.025 mm, respectively. For the infiltration data, where the soil texture is unknown, dg and Sg could not be calculated and the data field in the database was left empty. The database also contains the locations of the experimental sites in another dataset named locations.csv that provides the approximate latitude and longitudes in decimal degree (dd.dd) format.

In order to predict infiltration parameters for examined soils, we classified data sets into two groups of 1D and 3D conditions. Then infiltration parameters of 1D condition were predicted by fitting measured infiltration curves to three-parameter infiltration equation of Philip model (Kutílek and Krejča, 1987), Equation [3], while the infiltration parameters of 3D condition were predicted by fitting measured data to simplified form of Haverkamp et al. (1994), Equation [4]:


		I3D = S*√t + 0.47*Ks*t + A*t			Equation 3

		
		I1D = S*t^(1/2) + 0.33*Ks*t + A*t^(3/2)		Equation 4



The statistics for the fitting process as well as the fitted parameters of two mentioned models are reported in an additional dataset labelled Statistics. For soils excluded from analysis, a NaN value is reported.

------------------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------------------

Table 1- Description of the variables listed in database metadata file:

Column				Supplies:				
Code				Data set identifier with 4 digits from 0001 to 4936
Clay [%]			Mass of soil particles, < 0.002 mm
Silt [%]			Mass of soil particles, >0.002 and < 0.05 mm
Sand [%]			Mass of soil particle, > 0.05 and < 2 mm
Texture				1: Sand; 2: Loamy sand; 3: Sandy loam; 4: Sandy clay loam; 5: Sandy Clay; 				
                                6: Loam; 7: Silt loam; 8: Silt; 9: Clay loam; 10: Silty clay loam; 
				11: Silty clay; 12: Clay
Gravel [%]			Mass of particles larger than 2 mm
dg [mm]				Geometric mean diameter 
Sg				Standard deviation of soil particle diameter
OC [%]				Soil organic carbon content
Db [g cm-3]			Soil bulk density
Dp [g cm-3]			Soil particle density
Ksat [cm h-1]			Soil saturated hydraulic conductivity
WC_s [cm3 cm-3]			Saturated volumetric soil water content	
WC_i [cm3 cm-3]			Initial volumetric soil water content	
FC [cm3 cm-3]			Soil water content at field capacity
PWP [cm3 cm-3]			Soil water content at permanent wilting point (1500 kPa)
WC_r [cm3 cm-3]			Residual volumetric soil water content
WAS [%]				Wet-aggregate stability
MWD [mm]			Aggregates mean weight diameter
GMD [mm]			Aggregates geometric mean diameter
EC [dS m-1]			Soil electrical conductivity
pH				Soil acidity
Gypsum [%]			Soil gypsum content
CCE [%]				Soil carbonate calcium equivalent
CEC [Cmolc kg-1]		Soil cation exchange capacity
SAR [-]				Soil sodium adsorption ratio
DiscRadius [mm]			Applied disc radius (if any)
Instrument			Applied instruments for infiltration measurement:
				1: Double ring; 2: Single ring; 3: Rainfall simulator; 
				4: Guelph permeameter; 5: Disc infiltrometer; 6: Micro-infiltrometer; 					
                                7: Mini-infiltrometer; 8: Aardvark Permeameter; 
				9: Linear source method; 10: Point source method; 
				11: Hood infiltrometer; 12: Tension infiltrometer; 13: BEST method
Vegetation cover [%]		-
Land use			Dominant land-use or land cover type of the experimental site
Rainfall intensity [mm h-1]	The intensity of rainfall simulation
Slope [%]			The main slope of the experimental site
Treatment			Applied treatment in experimental site	
Crust				Yes: existence of crust; No: no crust layer	 
Sand contact layer		Yes: sand contact layer is applied during infiltration measurement; 
				No: no sand contact layer

------------------------------------------------------------------------------------------------------

SWIG database is supplementary to article "Development and Analysis of Soil Water Infiltration Global Database" submitted to ESSD Journal.

------------------------------------------------------------------------------------------------------
------------------------------------------------------------------------------------------------------

Authors list:

Mehdi Rahmati1,2,*, Lutz Weihermüller2,3, Jan Vanderborght2,3, Yakov A. Pachepsky4, Lili Mao5, Seyed Hamidreza Sadeghi6, Niloofar Moosavi2, Hossein Kheirfam7, Carsten Montzka2,3, Kris Van Looy2,3, Brigitta Toth8, Zeinab Hazbavi6, Wafa Al Yamani9, Ammar A. Albalasmeh10, Ma'in Z. Alghzawi10, Rafael Angulo-Jaramillo11, Antônio Celso Dantas Antonino12, George Arampatzis13, Robson André Armindo14, Hossein Asadi15, Yazidhi Bamutaze16, Jordi Batlle-Aguilar17,18,19, Béatrice Béchet20, Fabian Becker21, Günter Blöschl22,23, Klaus Bohne24, Isabelle Braud25, Clara Castellano26, Artemi Cerdà27, Maha Chalhoub17, Rogerio Cichota28, Milena Císlerová29, Brent Clothier30, Yves Coquet17,31, Wim Cornelis32, Corrado Corradini33, Artur Paiva Coutinho12, Muriel Bastista de Oliveira34, José Ronaldo de Macedo35, Matheus Fonseca Durães14, Hojat Emami36, Iraj Eskandari37, Asghar Farajnia38, Alessia Flammini33, Nándor Fodor39, Mamoun Gharaibeh10, Mohamad Hossein Ghavimipanah6, Teamrat A. Ghezzehei40, Simone Giertz41, Evangelos G. Hatzigiannakis13, Rainer Horn42, Juan José Jimenez43, Diederik Jacques44, Saskia Deborah Keesstra45,46, Hamid Kelishadi47, Mahboobeh Kiani-Harchegani6, Mehdi Kouselou1, Madan Kumar Jha48, Laurent Lassabatere11, Xiaoyan Li49, Mark A. Liebig50, Lubomír Lichner51, María Vitoria López52, Deepesh Machiwal53, Dirk Mallants54, Micael Stolben Mallmann55, Jean Dalmo de Oliveira Marques56, Miles R Marshall57, Jan Mertens58, Félicien Meunier59, Mohammad Hossein Mohammadi15, Binayak P Mohanty60, Mansonia Pulido Moncada61, Suzana Montenegro62, Renato Morbidelli33, David Moret-Fernández52, Ali Akbar Moosavi63, Mohammad Reza Mosaddeghi47, Seyed Bahman Mousavi1, Hasan Mozaffari63, Kamal Nabiollahi64, Mohammad Reza Neyshabouri65, Marta Vasconcelos Ottoni66, Theophilo Benedicto Ottoni Filho67, Mohammad Reza Pahlavan Rad68, Andreas Panagopoulos13, Stephan Peth69, Pierre-Emmanuel Peyneau20, Tommaso Picciafuoco22,33, Jean Poesen70, Manuel Pulido71, Dalvan José Reinert72, Sabine Reinsch57, Francis Parry Roberts57, David Robinson57, Jesús Rodrigo-Comino73,74, Otto Corrêa Rotunno Filho75, Tadaomi Saito76, Hideki Suganuma77, Carla Saltalippi33, Renáta Sándor39, Brigitta Schütt21, Manuel Seeger74, Nasrollah Sepehrnia78, Ehsan Sharifi Moghaddam6, Manoj Shukla79, Shiraki Shutaro80, Ricardo Sorando25, Ajayi Asishana Stanley81, Peter Strauss82, Zhongbo Su83, Ruhollah Taghizadeh-Mehrjardi84, Encarnación Taguas85, Wenceslau Geraldes Teixeira86, Ali Reza Vaezi87, Mehdi Vafakhah6, Tomas Vogel29, Iris Vogeler28, Jana Votrubova29, Steffen Werner88, Thierry Winarski11, Deniz Yilmaz89, Michael H. Young90, Steffen Zacharias91, Yijian Zeng83, Ying Zhao92, Hong Zhao83, Harry Vereecken2,3		

------------------------------------------------------------------------------------------------------

Affiliations:
1) Department of Soil Science and Engineering, Faculty of Agriculture, University of Maragheh, Maragheh, Iran; 
2) Forschungszentrum Jülich GmbH, Institute of Bio- and Geosciences: Agrosphere (IBG-3), Jülich, Germany; 
3) ISMC International Soil Modeling Consortium;
4) USDA-ARS Environmental Microbial and Food Safety Laboratory, Beltsville, MD 20705; 
5) Key Laboratory of Dryland Agriculture, Ministry of Agriculture, Institute of Environment and Sustainable Development in Agriculture, Chinese Academy of Agricultural Sciences, Beijing 100081, PR China; 
6) Department of Watershed Management Engineering, Faculty of Natural Resources, Tarbiat Modares University, Iran; 
7) Department of Environmental Sciences, Urmia Lake Research Institute, Urmia University, Urmia, Iran; 
8) University of Pannonia, Georgikon Faculty, Department of Crop Production and Soil Science Deák F. u. 16, Keszthely, 8360, Hungary; 
9) Environment Agency - Abu Dhabi, UAE; 
10) Department of Natural Resources and Environment, Faculty of Agriculture, Jordan University of Science and Technology, P.O. Box 3030, Irbid 22110, Jordan; 
11) Université de Lyon, Université Claude Bernard Lyon1, ENTPE, CNRS, UMR5023 LEHNA, F-69518, France; 
12) Universidade Federal de Pernambuco, Centro Acadêmico do Agreste, Núcleo de Tecnologia , Caruaru, Brazil; 
13) Hellenic Agricultural Organization, Soil and Water Resources Institute, 57400 Sindos, Greece; 
14) Núcleo de Atividades em Engenharia de Biossistemas (NAEB), DSEA-UFPR, Curitiba, PR, Brazil; 
15) Department of soil science engineering, Faculty of agriculture and natural resources, University of Tehran. Karaj. Iran; 
16) Department of Geography, Geo-Informatics and Climatic Sciences, Makerere University, P.O. Box 7062, Kampala, Uganda; 
17) UMR 1402 INRA AgroParisTech Functional Ecology and Ecotoxicology of Agroecosystems, Institut National de la Recherche Agronomique, AgroParisTech B.P. 01 F-78850 Thiverval-Grignon France; 
18) UMR 8148 IDES CNRS/Université Paris-Sud XI Bât. 504 Faculté des Sciences 91405 Orsay Cedex, France; 
19) Innovative Groundwater Solutions (IGS), Victor Harbor, 5211, South Australia, Australia; 
20) LUNAM Université, IIFSTTAR, GERS, EE, F-44344 Bouguenais, France; 
21) Freie Universität Berlin, Department of Earth Sciences, Institute of Geographical Sciences, Malteserstr. 74-100, Lankwitz, 12249, BERLIN, Germany; 
22) Centre for Water Resource Systems, TU Wien, Karlsplatz 13, 1040 Vienna, Austria; 
23) Institute of Hydraulic Engineering and Water Resources Management, TU Wien, Karlsplatz 13/222, 1040 Vienna, Austria; 
24) Faculty of Agricultural and Environmental Sciences, University of Rostock, Germany; 
25) RiverLy, Catchment Hydrology Group, Villeurbanne, France; 
26) Pyrenean Institute of Ecology-CSIC. AV. Montañana 1005 // Av. Victoria s / n. 50059 Zaragoza//22700 Jaca, Huesca. Spain; 
27) Soil Erosion and Degradation Research Group, Department of Geography, University of Valencia, Valencia, Spain;  
28) Plant and Food Research, Mount Albert Research Station, Auckland, New Zealand; 
29) Czech Technical University in Prague, Faculty of Civil Engineering, Thákurova 7, 166 29 Prague 6, Czech Republic; 
30) Plant & Food Research, Palmerston North, New Zealand;  
31) ISTO UMR 7327 Université d’Orléans, CNRS, BRGM, 45071 Orléans, France; 
32) Department of Soil Management, UNESCO Chair on Eremology, Ghent University, Belgium; 
33) Department of Civil and Environmental Engineering, University of Perugia, Perugia, Italy; 
34) UniRedentor University Center. BR 356, 25, Presidente Costa e Silva, Itaperuna, Rio de Janeiro, Brazil; 
35) Embrapa Solos, Rua Jardim Botânico, 1.024, CEP 22040-060,  Jardim Botânico, Rio de Janeiro, RJ, Brazil; 
36) Department of Soil Science, Faculty of Ferdowsi Mashhad, Mashhad, Iran; 
37) Dryland Agricultural Research Institute, Agricultural Research, Education and Extension Organization Maragheh, East Azerbaijan, Iran; 
38) Scientific Member of Soil and Water Research Department, East Azerbaijan Agricultural and Natural Resources Research and Education center, Iran;  
39) Agricultural Institute, Centre for Agricultural Research, Hungarian Academy of Sciences, Brunszvik str. 2., H-2462 Martonvásár, Hungary; 
40) Life and Environmental Sciences, University of California, Merced, United States; 
41) Geographisches Institut, Universität Bonn, Germany; 
42) Institute of Plant Nutrition and Soil Science, Christian-Albrechts-University zu Kiel, Olshausenstr. 40, 24118 Kiel, Germany; 
43) Instituto Pirenaico de Ecología, Spanish National Research Council (IPE-CSIC), Avda. Llano de la victoria 16, Jaca (Huesca), 22700, Spain; 
44) Belgian Nuclear Research Centre, Engineered and Geosystems Analysis, Belgium; 
45) Soil Physics and Land Management Group, Wageningen University, Droevendaalsesteeg 4 6708PB, Wageningen, The Netherlands; 
46) Civil, Surveying and Environmental Engineering, The University of Newcastle, Callaghan 2308, Australia; 
47) Department of Soil Science, College of Agriculture, Isfahan University of Technology, Isfahan 84156-83111, Iran; 
48) Agricultural & Food Engineering Department, Indian Institute of Technology Kharagpur, Kharagpur – 721302, West Bengal, India; 
49) State Key Laboratory of Earth Surface Processes and Resource Ecology, Faculty of Geographical Science, Beijing Normal University, Beijing 100875 China; 
50) Research Soil Scientist, USDA Agricultural Research Service,  P.O. Box 459, 1701 10th Ave., S.W. Mandan, ND  58554-0459, USA; 
51) Institute of Hydrology, Slovak Academy of Sciences, Bratislava, Slovakia; 
52) Departamento de Suelo y Agua, Estación Experimental de Aula Dei (EEAD), Consejo Superior de Investigaciones Científicas (CSIC), PO Box 13034, 50080 Zaragoza, Spain.; 
53) ICAR-Central Arid Zone Research Institute, Regional Research Station, Kukma – 370105, Bhuj, Gujarat, INDIA; 
54) CSIRO Land and Water, Glen Osmond, South Australia, Australia; 
55) PhD student at his first year. Soil Science Graduate Program (ufsm.br/ppgcs), Federal University of Santa Maria, state of Rio Grande do Sul, Brazil; 
56) Federal Institute of Education, Science and Technology of the Amazonas – IFAM, Campus Center of Manaus, Manaus, Brazil; 
57) Centre for Ecology and Hydrology, Environment Centre Wales, Deiniol Road, Bangor, Gwynedd LL57 2UW, UK; 
58) ENGIE Research and Technologies, Simon Bolivardlaan 34, 1000 Brussels, Belgium; 
59) Universite Catholique de Louvain, Earth and Life Institute-Environmental Sciences, Louvain-la Neuve, Belgium ;  
60) Dep. of Biological and Agricultural Engineering, 2117 TAMU, Texas A&M Univ., College Station, TX 77843-2117; 
61) Instituto de Edafologı´a, Facultad de Agronomı´a, Universidad Central de Venezuela, Venezuela; 
62) Universidade Federal de Pernambuco (UFPE), Av. Prof. Moraes Rego, 1235 - Cidade Universitária, Recife - PE - CEP: 50670-901. Brazil; 
63) Department of Soil Science, College of Agriculture, Shiraz University, Shiraz, Iran; 
64) Department of Soil Science and Engineering, Faculty of Agriculture, University of Kurdistan, Sanandaj, Kurdistan Province, Iran; 
65) Department of Soil Science, Faculty of Agriculture, University of Tabriz, Tabriz, Iran; 
66) Department of Hydrology, Geological Survey of Brazil (CPRM), Av. Pauster, 404. CEP 22290-240 Rio de Janeiro (RJ), Brazil.; 
67) Department of Water Resources and Environment, Federal University of Rio de Janeiro, Avenida Athos da Silveira Ramos, PO box: 68570, Rio de Janeiro, RJ, Brazil; 
68) Soil and Water Research Department, Sistan Agricultural and Natural Resources Research and Education Center, Agricultural Research, Education and Extension Organization (AREEO), Zabol, Iran; 
69) Department of Soil Science, University of Kassel, Nordbahnhofstr. 1a, 37213 Witzenhausen, Germany; 
70) Department of Earth and Environmental Sciences, Catholic University of Leuven, Geo-Institute, Celestijnenlaan 200E, 3001 Heverlee, Belgium; 
71) GeoEnvironmental Research Group, University of Extremadura, Faculty of Philosophy and Letters, Avda. de la Universidad s/n, 10071 Cáceres, Spain; 
72) Soil Science Department, Federal University of Santa Maria, state of Rio Grande do Sul, Brazil; 
73) Instituto de Geomorfología y Suelos, Department of Geography, University of Málaga, 29071, Málaga, Spain.; 
74) Department of Physical Geography, Trier University, D-54286 Trier, Germany; 
75) Civil Engineering Program, Alberto Luiz Coimbra Institute for Postgraduate Studies and Research in Engineering (COPPE), Federal University of Rio de Janeiro, Avenida Athos da Silveira Ramos, Rio de Janeiro, RJ, Brazil; 
76) Faculty of Agriculture, Tottori University, 4-101 Koyama-Minami, Tottori 680-8553, Japan; 
77) Department of Materials and Life Science, Seikei University, 3-3-1, Kichijoji-kitamachi, Musashino, Tokyo 180-8633, Japan; 
78) Department of Soil Science, College of Agriculture, Isfahan University of Technology, Isfahan, Iran; 
79) Plant and Environmental Sciences, New Mexico State University, Las Cruces, New Mexico; 
80) Japan International Research Center for Agricultural Science, Rural Development Division, Tsukuba, Japan; 
81) Department of Agricultural and Bio-Resources Engineerin, Faculty of Engineering, Ahmadu Bello University Zaria, Nigeria; 
82) Institute for Land and Water Management Research, Federal Agency for Water Management, Pollnbergstraße 1, 3252 Petzenkirchen, Austria; 
83) Department of Water Resources, ITC Faculty of Geo-Information Science and Earth Observation, University of Twente, Enschede, the Netherlands; 
84) Faculty of Agriculture and Natural Resources, Ardakan University, Ardakan, Yazd Province, Iran; 
85) University of Córdoba, Department of Rural Engineering, 14071 Córdoba, Spain; 
86) Soil Physics, Embrapa Soils, Rua Jardim Botaˆnico, 1026, 22460-00 Rio de Janeiro, RJ, Brazil; 
87) Department of Soil Science, Agriculture Faculty, University of Zanjan, Zanjan, Iran; 
88) Department of Geography, Ruhr-University Bochum, D-44799 Bochum, Germany; 
89) Engineering Faculty, Civil Engineering Department, Munzur University, Tunceli, Turkey; 
90) Bureau of Economic Geology, John A. and Katherine G. Jackson School of Geosciences, University of Texas at Austin, University Station, Box X, Austin, TX; 
91) UFZ Helmholtz Centre for Environ. Res., Monitoring and Exploration Technologies, Leipzig, Germany; 
92) College of Resources and Environmental Engineering, Ludong University, Yantai 264025, China
