hadoop fs -copyFromLocal C50/ /
./mahout seqdirectory -i /C50/C50train -o /seqreuters -xm sequential
./mahout seq2sparse -i /seqreuters -o /train-sparse
./mahout kmeans -i /train-sparse/tfidf-vectors/ -c /kmeans-train-clusters -o /train-clusters-final -dm org.apache.mahout.common.distance.EuclideanDistanceMeasure -x 10 -k 10 -ow
./mahout clusterdump -d /train-sparse/dictionary.file-0 -dt sequencefile -i /train-clusters-final/clusters-10-final -n 10 -b 100 -o ~/saida_clusters.txt -p /train-clusters-final/clustered-points
Lembrando que vocês deverão trocar alguns dos parâmetros aqui listados, como pastas e path dos arquivos e bases.
Clique em Atividade Prática para realizar a entrega
