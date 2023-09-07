# House-GAN++ (data-reader)


Code and instructions for converting rplan dataset (raster images) to [housegan++](https://github.com/ennauata/houseganpp) data format. 
[House-GAN++: Generative Adversarial Layout Refinement Network towards Intelligent Computational Agent for Professional Architects](https://arxiv.org/abs/2103.02574), CVPR 2021.
Project [website](https://ennauata.github.io/houseganpp/page.html).


 

Input Data
------
![alt text](https://github.com/motoki-sato627/Housegan-data-reader/blob/main/image/0.jpg "Sample")
<br/>
Data: [RPLAN dataset](http://staff.ustc.edu.cn/~fuxm/projects/DeepLayout/index.html), which offers 60k vector-graphics floorplans designed by professional architects. 
<br/>
 
Requirtments
------
   
```
pip install argparse
pip install numpy
pip install matplotlib
pip install shapely
pip install descartes
git clone https://github.com/motoki-sato627/Housegan-msd.git
cd Housegan-msd

```

How to run
------
  
```python raster_to_json.py --path ~/Desktop/dataset/msd_data```

Output data format
------

The data file (e.g., /sample_output/0.json).

```
ROOM_CLASS = {"living_room": 1, "kitchen": 2, "bedroom": 3, "bathroom": 4, "balcony": 5, "entrance": 6, "dining room": 7, "study room": 8,
              "storage": 10 , "front door": 15, "unknown": 16, "interior_door": 17}
              
              
# having room type in it
"room_type": [3, 4, 1, 3 ]

#bounding boxes per room        
"boxes: [[72.0, 161.0, 124.0, 220.0], [72.0, 130.0, 107.0, 157.0], [111.0, 28.0, 184.0, 203.0], [72.0, 87.0, 124.0, 126.0]] 

#first four entry are per list are rooms edges and 4th and 6th are showing what room type is on each side of edge 
"edges":[72.0, 161.0, 72.0, 220.0, 3, 0], ...,[107.0, 130.0, 72.0, 130.0, 4, 0], [148.0, 28.0, 148.0, 87.0, 1, 2]] 

#room indexes that are on each side of the edges
"ed_rm":[0], [0], [0], [0, 2], ..., [2], [2, 3], [2, 1], [2, 0], [2]] 
```



Citation
------
Please consider citing our work.
```
@inproceedings{nauata2021house,
  title={House-GAN++: Generative Adversarial Layout Refinement Network towards Intelligent Computational Agent for Professional Architects},
  author={Nauata, Nelson and Hosseini, Sepidehsadat and Chang, Kai-Hung and Chu, Hang and Cheng, Chin-Yi and Furukawa, Yasutaka},
  booktitle={Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition},
  pages={13632--13641},
  year={2021}
}
```

Contact
------
If you have any question, feel free to contact me at sepidh@sfu.ca

Acknowledgement
------
This research is partially supported by NSERC Discovery Grants, NSERC Discovery Grants Accelerator Supplements, DND/NSERC Discovery Grant Supplement, and Autodesk. We would like to thank architects and students for participating in our user study.

