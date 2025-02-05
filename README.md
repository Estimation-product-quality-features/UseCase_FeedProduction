# ProQualAI: Product Quality Tracking Tool on the Example of Agri-Food Industries 🌾 

### An intuitive and helpful software tool for estimating the product quality in process industries. As a case study, the production of flour in the context of the compound feed industry is shown.
The compound feed industry can produce many feed mixtures up to many different ingredients. Ingredients as agricultural raw materials, such as maize and wheat, are to be processed in these industries. Under rapidly and strongly fluctuating input raw materials and changing recipes, the condition of a process has to be continually tuned by process operators to satisfy the quality requirements. Flour is one popular feed due to its balanced nutrional nature and availability in various forms, for instance, in pellets. The schredding of natural raw materials leads to the required flour structure, which is relevant for further processing, such as mixing and pelleting, and ultimative relevant for the animal health.
After grinding, samples of produced flour are evaluated on its particle size using deep learning image processing methods. In this repo, we develop a quality traking tool that automatically detects, classifies and counts partially ground and unground seeds on image frames taken from the produced flour, so that engineers can subsequently use these results for evaluating the flour quality and adjusting better the grounding machine parameters in future production charges. 

<br>
<img src="./PQ_Framework/public/images/webpage_example.gif"/>
<br>

## About
ProQualAI consists of two packages: 
*  The package PQ_AImodels handles the deep learning image processing code for model creation. The models are created in Python3 and use mainly Tensorflow and its APIs ([TF API](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf1.md)) and comulative counting mode modules ([TF counting API](https://github.com/ahmetozlu/tensorflow_object_counting_api)).
*  The package PQ_Framework contains the design of a webpage, mainly in JS, which lets you run different image processing models in near real time, as well as visualize and download its outputs in a simple form. The framework was bootstrapped with [Create React App](https://github.com/facebook/create-react-app) and [Firebase](https://firebase.google.com/running) in a docker image to provide security and to help to build, run and deploy successfully models in the webpage. 

## 🧰 Requirements 

<a href="https://www.w3.org/html/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a> <a href="https://www.w3schools.com/css/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/javascript/javascript-original.svg" alt="javascript" width="40" height="40"/> </a> <a href="https://reactjs.org/" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/react/react-original-wordmark.svg" alt="react" width="40" height="40"/> </a> 
<br></br>
<a href="https://www.python.org" target="_blank"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a>
<a href="https://www.tensorflow.org" target="_blank"> <img src="https://www.vectorlogo.zone/logos/tensorflow/tensorflow-icon.svg" alt="tensorflow" width="40" height="40"/> </a> 
</a>
<br></br>
</a> <a href="https://firebase.google.com/" target="_blank"> <img src="https://www.vectorlogo.zone/logos/firebase/firebase-icon.svg" alt="firebase" width="40" height="40"/> </a>

## Installation
### PQ_AImodels
You can install the TensorFlow Object Detection API either with Python Package Installer (pip) or Docker. For local runs we recommend using Docker.
Clone the TensorFlow repository and proceed to one of the installation options.

```bash
git clone https://github.com/tensorflow/models.git
```

#### Docker Installation

```bash
# From the root of the git repository
docker build -f research/object_detection/dockerfiles/tf1/Dockerfile -t od .
docker run -it od
```

#### Python Package Installation

```bash
cd models/research
# Compile protos.
protoc object_detection/protos/*.proto --python_out=.
# Install TensorFlow Object Detection API.
cp object_detection/packages/tf1/setup.py .
python -m pip install --use-feature=2020-resolver .
```

```bash
# Test the installation.
python object_detection/builders/model_builder_tf1_test.py
```

### PQ_Framework
In order to run the webpage locally, you can first clone the repository and then run the node package manager via: 
> npm install 
> npm start  

For the deployment of firebase build a production optimized webpage using  
> npm run build 

For deploying the webpage to firebase, please login to your firebase  
> ``` firebase login ``` 

Follow the link and enter your credentials associated with firebase. The next step is to initialize firebase hosting using  

> ``` firebase init hosting ```

Follow the instructions and choose the PQFramework as the projekt you want to deploy to. Note that as "public directory" **build** has to be specified. Additionally the page should be rewritten as single page. When asking to overwrite existing files, the answer is "No".  

Finally deploy the webpage using 

> ``` firebase deploy --only hosting ```

A url should be displayed which you can use to visit your webpage online in.

## Documentation
Our SoftwareX paper: "ProQualAI: A software to compute qualitative and quantitative product features in process industries using deep learning image processing algorithms" provides a concise description of the software. 
The code documentation is provided along the relevant code lines.

## Contributing
Pull requests for minor changes are welcome. For major changes, please open an issue or fork the repository first to discuss what you would like to change. In oder words:

* Issue: If you spotted a bug, have an idea for an improvement or a new feature, please open a issue. Please open an issue in both cases: If you want to work on in yourself and if you want to leave it to us to work on it.
* Fork: If you want to work on an issue yourself please fork the repository, then develop the feature in your copy of the repository and finally file a pull request to merge it into our repository.

## Cite
If you are using ProQualAI in your academic work please cite it by referencing our [SoftwareX paper](https://todo): 

M.T. Alvela Nieto, H. Gelbhardt, J.-H. Ohnlendorf, K.-D. Thoben: "ProQualAI: A software to compute qualitative and quantitative product features in process industries using deep learning image processing algorithms". Accepted by SoftwareX.
## License
This software is licensed under the MIT license. For more information, read the file [MIT](https://choosealicense.com/licenses/mit/)

