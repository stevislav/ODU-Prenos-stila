# Generisanje umetničkih dela pomoću neuronskog prenosa stila

Učitavaju se slike sadržaja i stila i skaliraju se na jednake vrednosti (hiperparametar IMAGE_SIZE)  
Korištena već trenirana konvolucijska neuronska mreža VGG-16 (moguće koristiti i VGG-19)  
Moguće je razlikovati slojeve koji su odgovorni za stil i one koji su odgovorni za sadržaj, pa se oni mogu razdvojiti kako bi posebno radili na sadržaju i stilu.  


Funkcije:
* content_loss - minimizujemo rastojanje između ulazne i izlazne slike, težimo očuvanju sadržaja.
* compute_style_loss - minimizujemo rastojanje između stila i izlazne slike, težimo da primenimo novi stil.
* total_variation_loss - služi za regularizaciju, smanjenje šuma na izlazu.

Na kraju se postavljaju gradijenti i primenjuje [Limited-memory BFGS](https://en.wikipedia.org/wiki/Limited-memory_BFGS) algoritam.

Korisne stvari:  
[VGG](https://keras.io/api/applications/vgg/) implementacija  
[IST](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf) Image Style Transfer  
[CNN](https://www.vlfeat.org/matconvnet/pretrained/) već istrenirane neuronske mreže

Zavisnosti:
* Keras
* Tensorflow
* Numpy
* Scipy
* Pillow

Program pokrenuti kao Jupyter svesku, ili preko Google Colab
