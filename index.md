# Hippocampal Neuropil in 3DEM: A Resource to Train Users, Model Data, and Enhance Autosegmentation Tools

<a name="data-guide"></a>
## Data Guide 

This dataset contains three volumes of hippocampal CA1 neuropil from adult rat. Images and traces are available for three distinct regions:

  * A cube (~10 um^3) surrounding a large dendritic spine
  * A cylinder (~43 um^3) surrounding an oblique dendritic segment (3.4 um long)
  * An irregular rectangle (~178 um^3) surrounding an apical dendritic segment (4.9 um long) 

**Open Connectome** (OCP) web visualization "sliders" further subdivide data into the following categories:

  * Axons
  * Dendrites
  * Synapses
  * Glia
  * Sub-cellular Components
        * Smooth Endoplasmic Reticulum
        * Polyribosomes
        * Mitochondria and Microtubules
        * Endosomal Compartments 

**RECONSTRUCT** files provide unique names for visualization of each object, section by section traces, calibration, and quantification as summarized here (see also TABLES 2-4 of the MANUSCRIPT). 

  * Axons: `AX` or `ax##(#)suffix`
     * AX distinguishes identity stamps from membrane boundary traces (ax) for unique axons ##(#), where 3 numbers indicate more than 100 in the volume. 
     * Suffixes A, B are for different branches of the same axon.
     * Suffixes e, i, u, m are for excitatory, inhibitory, unidentified (not distinguished as either excitatory or inhibitory within the reconstructed volume), and myelinated axons.
  * Dendrites: D or d##(#)suffix:
     * D distinguishes identity stamps from membrane boundary traces (d) for dendrites, where 3 numbers ##(#) indicate more than 99 in the volume.
        * Most dendrites are spiny and have no suffix in their names
     * Suffix "in" -- distinguishes an interneuron dendrite
     * Suffixes A, B -- different branches of the same dendrite
     * Suffix p## -- protrusion stamps at the origins of spines and shaft synapss along d##(#)
     * "spinule##" - stamp identifying a specific spinule traced from d##(#)
     * "SP or sp##" -- spine fragment stamp or trace not connected to a dendrite in volume
  * Synapses
     * "cfa" - flat areas used to quantify apposition areas of synapses
        * d##cfa##Ax##(#)(i,e), sp##cfa##Ax##(#)(i,e);(a,b,c...) -- note that the names include specific names of the dendrites and axons that make the synapses
     * "c" -- encircled synapse appositions to make 3D objects for visualization
        * d##c##Ax##(#)(i,e), sp##c##Ax##(#)(i,e);(a, b, c...)
  * Glia: ag, mg#, og, my##(#)
     * Astroglia (ag) -- likely to be from just one in each of these small volumes
     * Microglia (mg) -- two identified in the Apical volume
     * Oligodendrioglia (og) -- not individually distinguished for the cell bodies
     * Myelin (my) -- numbered by the axon number they surround
  * Sub-cellular Components
     * Smooth Endoplasmic Reticulum and Spine Apparatus
        * d###ser -- part of the continuous network of a particular dendrite's SER
        * d###ser-like -- membrane bound structures that have SER appearance, but were not connected within the 3D volume 
        * d###sa(n,h)## -- spine apparatus located in the (n)eck or (h)ead
     * Polyribosomes: d###r(s,b,n,h)##
        * Stamps indicate locations in dendrite (s)haft; spine (b)ase, (n)eck, or (h)ead
     * Mitochondria and Microtubules
        * d###mito## -- each mitochondrion in each dendrite has a unique number
        * d###mt## -- each microtubule in each dendrite has a unique number 
     * Endosomal compartments are named for the dendrites in which they occur:
        * amorphous vesicle (d###av##)
        * autophagosome (d###autophagosome##)
        * coated pit (d###cp##)
        * coated vesicle (d###cv##)
        * larger vesicle (d###ves##)
        * lysosome (d###lys##)
        * multivesicular body (d###mvb##)
        * mvb vesicles (d###mvb##v##)
        * small vesicle (d###sv##)
        * tubule (d###te##)
        * vacuole (d###vac##)

For further explanation please see: 

   * [Manuscript](http://www.nature.com/articles/sdata201546) 
   * [SynapseWeb at NeuroData](http://openconnecto.me/synapseweb)
   * [SynapseWeb](https://sites.cns.utexas.edu/synapseweb)
   * [Reconstruct](https://sites.cns.utexas.edu/synapseweb/software-0)

<a name="datasets"></a>
### OCP Datasets 

| Dataset | XY Dimension | XY Base Resolution | Z Slices | Z Resolution |
|---------+--------------+--------------------+----------+--------------+
| Apical Volume | 8192 x 8192 | ~2 nm | 0 - 194 | ~50-60 nm |
| Oblique Volume | 8192 x 8192 | ~2 nm | 0 - 91 | ~50-60 nm |
| Spine Volume | 9000 x 9000 | ~2 nm | 30 - 89 | ~50-60 nm |

#### Resolution Hierarchy 
For each data set, the original image files were scaled in XY to three lower resolutions. The resolution hierarchy for each dataset is listed in the table below. 

| Dataset | Resolution 0 | Resolution 1 | Resolution 2 | Resolution 3 |
|---------+--------------+--------------+--------------+--------------+ 
| Apical Volume | 8192 x 8192 x 195 | 4096 x 4096 x 195 | 2048 x 2048 x 195 | 1024 x 1024 x 195 |
| Oblique Volume | 8192 x 8192 x 92 | 4096 x 4096 x 92 | 2048 x 2048 x 92 | 1024 x 1024 x 92 |
| Spine Volume | 9000 x 9000 x 59 | 4500 x 4500 x 59 | 2250 x 2250 x 59 | 1125 x 1125 x 59 |

The Z direction (distance between each XY image) is also scaled to maintain the original shape of the volume. Z-scaling for each dataset is identical, since all datasets were imaged in the same way. 

#### OCP Data Visualization 

All images and annotations are available in [CATMAID](http://openconnecto.me/catmaid/?dataview=36), our 2D web viewer. Annotations are grouped into four sets: Axons, Dendrites, Glia, and Synapses. The apical volume is further subdivided into the primary annotations (as referenced earlier), and Sub-cellular Components, which are grouped by Endosomal Components, Polyribosomes, Smooth Endoplasmic Reticulum and Spine Apparatus, and Mitochondria and Microtubules. Each set can be independently controlled by the sliders on the left side of the screen. Each dataset is available at the link below. 

  * [Apical Volume](http://openconnecto.me/catmaid/?pid=66&tool=navigator&sid0=103&s0=1) (primary annotations)
  * [Apical Volume](http://openconnecto.me/catmaid/?pid=66&tool=navigator&sid0=106&s0=1) (sub-cellular components)
  * [Oblique Volume](http://openconnecto.me/catmaid/?pid=67&tool=navigator&sid0=104&s0=1)
  * [Spine Volume](http://openconnecto.me/catmaid/?pid=65&tool=navigator&sid0=102&s0=1)

<a name="download-data"></a>
### Download Data 

#### Image Files 

Raw image and annotation data can be directly accessed using either a [web form](http://openconnecto.me/ocp/ocpuser/download/) or the following URL format:

    http://openconnecto.me/ocp/ca/[[token]]/[[cutout arguments]]

where `token` is a dataset token (see below) and `cutout arguments` are the output format, resolution, and x, y, and z dimensions. Subvolumes of the database may be downloaded as HDF5 and zipped Numpy arrays. Also, image planes may be viewed in a Web browser.  The following URL would cutout a 1000x1000x40 voxel region at resolution 1 of the project with token `kharris15apical`.

    http://openconnecto.me/ocp/ca/kharris15apical/hdf5/1/2000,3000/2000,3000/80,120/

Replace `hdf5` with `npz` for numpy formatted arrays. 

For more information on the cutout service, see the [NDStore Data API Documentation](http://docs.neurodata.io/ndstore/api/data_api.html). 

#### Reconstruct Files 

Unaligned images and reconstruct project files are available at the links below. The RECONSTRUCT software and its associated user manual are also available.

| Available Downloads ||
|--------------------|--------|
| Apical Volume | [.tar.gz](http://openconnecto.me/harrisdata/apical_volume.tar.gz) | [.zip](http://openconnecto.me/harrisdata/apical_volume.zip) |
| Oblique Volume | [.tar.gz](http://openconnecto.me/harrisdata/oblique_volume.tar.gz) | [.zip](http://openconnecto.me/harrisdata/oblique_volume.zip) |
| Spine Volume | [.tar.gz](http://openconnecto.me/harrisdata/spine_volume.tar.gz) | [.zip](http://openconnecto.me/harrisdata/spine_volume.zip) |
| Reconstruct | [Software](http://openconnecto.me/harrisdata/reconstruct/recon1101win32.exe) | [Help](http://openconnecto.me/harrisdata/reconstruct/manual.chm) |

To open data files in RECONSTRUCT, see our brief reconstruct guide (ABTODO: link?) below. 

<a name="data-tools"></a>
### Data Tools 
Three data tools are provided to interact with the data. 

#### RECONSTRUCT 

RECONSTRUCT provides a graphical user interface enabling quantitative analysis on the EM data. Data in RECONSTRUCT file format, along with the RECONSTRUCT program, is available for download [here](http://openconnecto.me/harrisdata/reconstruct/recon1101win32.exe). 

All annotations in these datasets were created using RECONSTRUCT. RECONSTRUCT supports a wide variety of 3DEM analyses: Data files, calibration, image alignment, section thickness estimation, tracing, naming, 3D reconstruction, and quantitative analyses are all supported. To use RECONSTRUCT, the end user must first download all data files for a requested volume (available above), and then open the main `ser` file for the dataset. The `ser` file names for each of the three volumes are enumerated below. 
   * Volumejosef.ser
   * R34js-gs.ser
   * recon_k24b.ser

For more information, see [https://sites.cns.utexas.edu/synapseweb/software-0](https://sites.cns.utexas.edu/synapseweb/software-0).

#### TrakEM2 
For users who are familiar with TrakEM2, one can open RECONSTRUCT data files in TrackEM2 via select `File → Import Reconstruct Project`. Browse to the .ser file for the dataset you want to open, and select it. TrackEM2 will load the Reconstruct project. See [http://fiji.sc/Reconstruct_Reader](http://fiji.sc/Reconstruct_Reader) for more. 

#### CAJAL 
CAJAL provides a Matlab interface to data stored in Open Connectome. Users can download data and store it in Matlab objects. Visualization tools are also available, allowing a user to page through data in 2D. Exporting 2D images and creating 2D movies is also supported. For more information and to download the software, see [https://github.com/openconnectome/cajal](https://github.com/openconnectome/cajal). 

A sample script for downloading and visualizing data in Matlab is provided below: 
{% gist alexbaden/e80d1587ecf995900ed3 %}

### Tokens for Data Access 
The following tokens are used for accessing raw data in OCP (either via the Matlab API or Web service).

#### Image (EM) Data 

| Token | Dataset |
|-------+---------|
| kharris15apical | Apical Volume |
| kharris15oblique | Oblique Volume |
| kharris15spine | Dendritic Volume |

#### Annotations / Tracings 

| Token | Group | Dataset |
|-------+-------+---------|
| kharris15apical_anno | All Annotations | Apical Volume |
||||
| kharris15oblique_anno | All Annotations | Oblique Volume |
||||
| kharris15spine_anno | All Annotations | Dendritic Volume |