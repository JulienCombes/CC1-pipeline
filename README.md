# CC1-pipeline

Partie 1 : 
1. J'ai ajouté "destination_s3_bucket.tf et "kinesis_datastream.tf"

2. J'ai changé les fichiers "destination_s3_bucket.tf" et "kinesis_datastream.tf"

Dans le fichier "destination_s3_bucket.tf" j'ai changé les lignes suivantes : 
  resource "aws_s3_bucket" "summary_destination" {
  bucket = "analytics-destination-julien-combes"
     Name        = "S3 bucket - Julien"
     
Dans le fichier "kinesis_datastream.tf" j'ai changé les lignes suivantes : 
resource "aws_kinesis_stream" "datastream_ingestion" {
  name        = "datastream_ingestion"
 

elle permet d’écrire dans des flux de Amazon Kinesis Data Streams à l'aide de Kinesis Agent
il permet l’installation des composantes dans la VM EC2 pour l’exécution de l’aplication
son role est de collecter et formater les logs afin de les envoyer à kinesis data stream

3. Voir capture d'écran

5. La partie user_data consiste à lancer des configs sur l'instance afin de tout paramétrer au lancement avec des données utilisateurs

6. L'agent Kinesis permet de stocker et de reformater les logs dans le bon format puis de les transférer à Kinesis data Stream.

Partie 2:

1. Pour la partie Ingestion nous utilisons les logs du fichier python via le service dataStream qui le lit grâce au fichier producer. 

2. Pour la partie Stockage nous utilisons AWS S3 pour stocker le stream de destination dans une bucket et pour transporter les données nous utilisons le serive Kinesis Firehose.

3. Pour la partie Transformation, nous utilisons le service Kinesis Data Analytics qui va transformer les données.

4. Pour la partie exploitation c'est via des requêtes SQL.

Partie 3:

5. Les fichiers arrivent avec un certain délai car elles ont une forte latence du au service utilisé.

6. Pour pour pouvoir s'authentifier et avoir un id.
