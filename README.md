# FB15k-CVT Dataset

This is the FB15k-CVT dataset, a knowldge graph that exapnds the original FB15k-237 dataset.
...

## File Structure 

The dataset is organized into two main folders :

- `Knowledge Graphs`: contains the original FB15k-CVT knowledge graph (`FB15k-CVT.nt`) in N-Triples format. Also contains `FB15k-CVT_Aux.nt` KG which is an extension of FB15k-CVT with additional entities (defined with MIDs) in relation with entities of type `CVT`.
- `Stratified Dataset`: contains the stratified train/validation/test splits of the FB15k-CVT dataset, as well as the quadruples used for the evaluation.

The folder structure is as follows:
```
+ KnowledgeGraph
|--- FB15k-CVT.nt
|--- FB15k-CVT_Aux.nt 
+ Stratified
|--- train.nt
|--- valid.nt
|--- test.nt
|--- +Quadruples
       |--- valid_t1.csv
       |--- valid_t2.csv
       |--- valid_t3.csv
       |--- test_t1.csv
       |--- test_t2.csv
       |--- test_t3.csv
```
- `train.nt`, `valid.nt`, and `test.nt` contain the triples for the train, validation, and test sets, respectively, in N-Triples format.
- `Quadruples` contains the quadruples used for evaluation, split into three sets (`t1`, `t2`, and `t3`, that) for each of the validation and test sets. Each quadruple is represented as a CSV file with four columns: (`Entity_01`, `relation_01`, `relation_02`, `Entity_02`). Each set corresponds to a different type of evaluation scenario:
  - Direct paths (`t1`): These quadruples are used for evaluating the model on (i) chain backward prediction task i.e., (?, 𝑟1, 𝑛_cvt)/(𝑛_cvt, 𝑟2, 𝑒2), (ii) chain forward prediction task  i.e., (𝑒1, 𝑟1, 𝑛_cvt).
  - Splitting paths (`t2`): for (iii) join prediction task i.e., (𝑒1, 𝑟1, 𝑛cvt)/(?, 𝑟2, 𝑛cvt)
  - Joining paths (`t3`): for (iv) split prediction task i.e., (𝑛cvt, 𝑟1, 𝑒1)/(𝑛cvt, 𝑟2, ?)
 
## Citation

If you use this dataset in your research, please cite the following paper:

```
Mouloud Iferroudjene, Victor Charpenay and Antoine Zimmermann. (2023, July). "FB15k-CVT: A Challenging Dataset for Knowledge Graph Embedding Models." In NeSy 2023, 17th International Workshop on Neural-Symbolic Learning and Reasoning.
```

## License

This dataset is released under the Creative Commons Attribution ...
