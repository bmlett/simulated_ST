# toy set ~100 spots 

# Set up
**Note**  
- updated script one of they ST_Simulate software to be more flexiable if the features did not match eactly between the two file inputs 
- the csv file indexes were updated to be the ID_CB-vento18 to match those within the count matrix file

**Step 1** split the data  
```
mkdir toyData
python3.6 ../../ST_simulation/split_sc.py vento18_10x.processed.h5ad FetalMaternal-Decidua-cellType_BL.csv --annotation_col annotated_cell_identity.ontology_label --out_dir toyData/
```
Seed = 59 749 507  
Total outputs = 12 and include:
- counts_validation_{seed}.p
- labels_validation_{seed}.p
- counts_generation_{seed}.p
- labels_generation_{seed}.p

**Step 2** design matrix  
```
python3.6 ../../ST_simulation/assemble_design.py 59 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir toyData/
python3.6 ../../ST_simulation/assemble_design.py 749 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir toyData/
python3.6 ../../ST_simulation/assemble_design.py 507 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir toyData/
```

Total outputs = 3 and include:
- synthetic_ST_seed59_design.csv
- synthetic_ST_seed749_design.csv
- synthetic_ST_seed507_design.csv  
design used for the simulation and includes the following information: 
- uniform = is the cell type uniformly located across spots (1) or localized in a small subset of spots (0) 
- density = is the cel type present in a spot at low desity (1) or high (0)
- nspots = total number of spots in which the cell type is located 
- mean_ncell = mean number of cells per spot

**Step 3** Assemble cell type composition per spot   
```
python3.6 ../../ST_simulation/assemble_composition.py 59 --tot_spots=100 --out_dir toyData/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_composition.py 749 --tot_spots=100 --out_dir toyData/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_composition.py 507 --tot_spots=100 --out_dir toyData/ --annotation_col annotated_cell_identity.ontology_label
```

Total outputs 3 and include:  
- synthetic_ST_seed59_1_composition.csv
- synthetic_ST_seed749_1_composition.csv
- synthetic_ST_seed507_1_composition.csv

**Step 4** Assemble simulated ST spots  
```
python3.6 ../../ST_simulation/assemble_st.py 59 --out_dir toyData/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_st.py 749 --out_dir toyData/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_st.py 507 --out_dir toyData/ --annotation_col annotated_cell_identity.ontology_label
```

Total outputs 6 and include: 
-  synthetic_ST_seed59_1_umis.csv
-  synthetic_ST_seed59_1_counts.csv
-  synthetic_ST_seed749_umis.csv
-  synthetic_ST_seed749_1_counts.csv
-  synthetic_ST_seed507_1_umis.csv
-  synthetic_ST_seed507_1_counts.csv

## Set2

**Step 1** split the data for another set of spots 
```
mkdir set2
python3.6 ../../ST_simulation/split_sc.py vento18_10x.processed.h5ad FetalMaternal-Decidua-cellType_BL.csv --annotation_col annotated_cell_identity.ontology_label --out_dir set2/
```
Seed = 416 459 879  
**Step 2** design matrix  
```
python3.6 ../../ST_simulation/assemble_design.py 416 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir set2/
python3.6 ../../ST_simulation/assemble_design.py 459 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir set2/
python3.6 ../../ST_simulation/assemble_design.py 879 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir set2/
```

**Step 3** Assemble cell type composition per spot   
```
python3.6 ../../ST_simulation/assemble_composition.py 416 --tot_spots=100 --out_dir set2/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_composition.py 459 --tot_spots=100 --out_dir set2/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_composition.py 879 --tot_spots=100 --out_dir set2/ --annotation_col annotated_cell_identity.ontology_label
```

**Step 4** Assemble simulated ST spots  
```
python3.6 ../../ST_simulation/assemble_st.py 416 --out_dir set2/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_st.py 459 --out_dir set2/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_st.py 879 --out_dir set2/ --annotation_col annotated_cell_identity.ontology_label
```

## Set3

**Step 1** split the data for another set of spots 
```
mkdir set3
python3.6 ../../ST_simulation/split_sc.py vento18_10x.processed.h5ad FetalMaternal-Decidua-cellType_BL.csv --annotation_col annotated_cell_identity.ontology_label --out_dir set3/
```
Seed = 108 598 411
**Step 2** design matrix  
```
python3.6 ../../ST_simulation/assemble_design.py 108 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir set3/
python3.6 ../../ST_simulation/assemble_design.py 598 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir set3/
python3.6 ../../ST_simulation/assemble_design.py 411 --tot_spots 100 --annotation_col annotated_cell_identity.ontology_label --out_dir set3/
```

**Step 3** Assemble cell type composition per spot   
```
python3.6 ../../ST_simulation/assemble_composition.py 108 --tot_spots=100 --out_dir set3/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_composition.py 598 --tot_spots=100 --out_dir set3/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_composition.py 411 --tot_spots=100 --out_dir set3/ --annotation_col annotated_cell_identity.ontology_label
```

**Step 4** Assemble simulated ST spots  
```
python3.6 ../../ST_simulation/assemble_st.py 108 --out_dir set3/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_st.py 598 --out_dir set3/ --annotation_col annotated_cell_identity.ontology_label
python3.6 ../../ST_simulation/assemble_st.py 411 --out_dir set3/ --annotation_col annotated_cell_identity.ontology_label
```
