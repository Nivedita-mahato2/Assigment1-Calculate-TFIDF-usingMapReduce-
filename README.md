# Assigment1-Calculate-TFIDF-usingMapReduce-

#for calculating TFIDF using Mapreduce the code was executed in 3 phases, to execute python files on jar to obtain TF-IDF of each of the term present in file with respect to the owner who commented it.

Phase 1:
 hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar -file /home/nivedita_mahato2/new/MapperPhaseOne.py  -mapper "python MapperPhaseOne.py"  -file /home/nivedita_mahato2/new/ReducerPhaseOne.py -reducer  "python ReducerPhaseOne.py" -input hdfs://cluster-d709-m/cloud/resultmap.txt -output  hdfs://cluster-d709-m/cloud/output30

Phase 2:
 hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar -file /home/nivedita_mahato2/MapperPhaseTwo.py  -mapper "python MapperPhaseTwo.py"  -file /home/nivedita_mahato2/ReducerPhaseTwo.py -reducer  "python ReducerPhaseTwo.py" -input hdfs://cluster-d709-m/cloud/output30 -output  hdfs://cluster-d709-m/cloud/output31

Phase 3: 
hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar -file /home/nivedita_mahato2/MapperPhaseThree.py  -mapper "python MapperPhaseThree.py"  -file /home/nivedita_mahato2/ReducerPhaseThree.py -reducer  "python ReducerPhaseThree.py" -input hdfs://cluster-d709-m/cloud/output31 -output  hdfs://cluster-d709-m/cloud/output32

