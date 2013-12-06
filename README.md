CREATE TABLE Event (
	Num NUMBER (10) NOT NULL,
	Nom VARCHAR (50) NOT NULL,
	Detail VARCHAR (500) NOT NULL,
	PRIMARY KEY (Num)
);

CREATE TABLE Offre (
	Num NUMBER (10) NOT NULL,
	Nom VARCHAR (50) NOT NULL,
	Detail VARCHAR (500) NOT NULL,
	Image VARCHAR (200), //chemin d'accès à l'image, peut être nul
	PRIMARY KEY (Num)
);

CREATE TABLE Bien (
	Nom VARCHAR (50) NOT NULL,
	Prix NUMBER (10) NOT NULL
	CONSTRAINT C1_Prix CHECK (Prix > 0),
) INHERITS (Offre);

CREATE TABLE RDV (
	NbPersonnes NUMBER (3) NOT NULL,
	Date VARCHAR (10) NOT NULL
	CONSTRAINT C1_NbPersonnes CHECK (NbPersonnes > 0)
) INHERITS (Offre);

CREATE TABLE Service (
	Heure NUMBER (2) NOT NULL,
	Date VARCHAR (10) NOT NULL,
	Competences VARCHAR (500) NOT NULL,
	CONSTRAINT C1_Heure CHECK (Heure >= 0),
	CONSTRAINT C2_Heure CHECK (Heure <= 24),
) INHERITS (Offre);


________________________

# pour une clé étrangère
Vérifier format adresse mail correct (détecter un @ et une extension d'adresse valide)
Email char (50) NOT NULL, CHECK (Email LIKE "%@%")

