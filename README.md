## Modificacion ITM

### configurar project
```sh
git lfs pull

pip install -r requirement.txt
```
### train model
```sh
python t_eletro_view.py
```
### run model
```sh
python electro_view.py
```
# A Benchmark for Visual Identification of Defective Solar Cells in Electroluminescence Imagery

This repository provides a dataset of solar cell images extracted from
high-resolution electroluminescence images of photovoltaic modules.

![An overview of images in the dataset. The darker the red is, the higher is the
likelihood of a defect in the solar cell overlayed by the corresponding color.](./doc/images/overview.jpg)

## The Dataset

The dataset contains 2,624 samples of 300x300 pixels 8-bit grayscale images of
functional and defective solar cells with varying degree of degradations
extracted from 44 different solar modules. The defects in the annotated images
are either of intrinsic or extrinsic type and are known to reduce the power
efficiency of solar modules.

All images are normalized with respect to size and perspective.
Additionally, any distortion induced by the camera lens used to capture the EL images was
eliminated prior to solar cell extraction.

## Annotations

Every image is annotated with a defect probability (a floating point value
between 0 and 1) and the type of the solar module (either mono- or
polycrystalline) the solar cell image was originally extracted from.

The individual images are stored in the `images` directory and the corresponding
annotations in `labels.csv`.

## Usage

In Python, use `utils/elpv_reader` in this repository to load the images and the
corresponding annotations as follows:

```python
from elpv_reader import load_dataset
images, proba, types = load_dataset()
```

The code requires NumPy and Pillow to work correctly.

## Citing

If you use this dataset in scientific context, please cite the following
publications:

> Buerhop-Lutz, C.; Deitsch, S.; Maier, A.; Gallwitz, F.; Berger, S.; Doll, B.; Hauch, J.; Camus, C. & Brabec, C. J. A Benchmark for Visual Identification of Defective Solar Cells in Electroluminescence Imagery. European PV Solar Energy Conference and Exhibition (EU PVSEC), 2018. DOI: [10.4229/35thEUPVSEC20182018-5CV.3.15](http://dx.doi.org/10.4229/35thEUPVSEC20182018-5CV.3.15)

> Deitsch, S.; Buerhop-Lutz, C.; Maier, A. K.; Gallwitz, F. & Riess, C. Segmentation of Photovoltaic Module Cells in Electroluminescence Images. CoRR, 2018, [abs/1806.06530](https://arxiv.org/abs/1806.06530)

> Deitsch, S.; Christlein, V.; Berger, S.; Buerhop-Lutz, C.; Maier, A.; Gallwitz, F. & Riess, C. Automatic classification of defective photovoltaic module cells in electroluminescence images. Solar Energy, Elsevier BV, 2019, 185, 455-468. DOI: [10.1016/j.solener.2019.02.067](http://dx.doi.org/10.1016/j.solener.2019.02.067)

BibTeX details:

<details>
  
```bibtex

@InProceedings{Buerhop2018,
  author    = {Buerhop-Lutz, Claudia and Deitsch, Sergiu and Maier, Andreas and Gallwitz, Florian and Berger, Stephan and Doll, Bernd and Hauch, Jens and Camus, Christian and Brabec, Christoph J.},
  title     = {A Benchmark for Visual Identification of Defective Solar Cells in Electroluminescence Imagery},
  booktitle = {European PV Solar Energy Conference and Exhibition (EU PVSEC)},
  year      = {2018},
  eventdate = {2018-09-24/2018-09-28},
  venue     = {Brussels, Belgium},
  doi       = {10.4229/35thEUPVSEC20182018-5CV.3.15},
}

@TechReport{Deitsch2018,
  Title            = {Segmentation of Photovoltaic Module Cells in Electroluminescence Images},
  Author           = {Sergiu Deitsch and Claudia Buerhop-Lutz and Andreas K. Maier and Florian Gallwitz and Christian Riess},
  Year             = {2018},
  Archiveprefix    = {arXiv},
  Eprint           = {1806.06530},
  Journal          = {CoRR},
  Url              = {http://arxiv.org/abs/1806.06530},
  Volume           = {abs/1806.06530}
}


@Article{Deitsch2019,
  author    = {Sergiu Deitsch and Vincent Christlein and Stephan Berger and Claudia Buerhop-Lutz and Andreas Maier and Florian Gallwitz and Christian Riess},
  title     = {Automatic classification of defective photovoltaic module cells in electroluminescence images},
  journal   = {Solar Energy},
  year      = {2019},
  volume    = {185},
  pages     = {455--468},
  month     = jun,
  issn      = {0038-092X},
  doi       = {10.1016/j.solener.2019.02.067},
  publisher = {Elsevier {BV}},
}
```
</details>

## License

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.

For commercial use, please contact us for further information.