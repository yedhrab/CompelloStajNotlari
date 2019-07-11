# Fotoşop Algılama <!-- omit in toc -->

Resmin orjinal olup olmadığını algılama ve eklenen verilerin tespiti

![ex_trampped](res/ex_trampped.png)

## İçerikler <!-- omit in toc -->

- [Temel Ayırma Teknikleri](#Temel-Ay%C4%B1rma-Teknikleri)
  - [EXIF MetaData ile Ayırma](#EXIF-MetaData-ile-Ay%C4%B1rma)
- [Error Level Analysis ile Ayırma](#Error-Level-Analysis-ile-Ay%C4%B1rma)
- [Noise Analysis ile Ayırma](#Noise-Analysis-ile-Ay%C4%B1rma)
- [Code Kısmı](#Code-K%C4%B1sm%C4%B1)
- [Yapılacaklar](#Yap%C4%B1lacaklar)
- [Ek Bağlantılar](#Ek-Ba%C4%9Flant%C4%B1lar)
- [Referanslar](#Referanslar)

## Temel Ayırma Teknikleri

![all_confidency_matrix](res/all_confidency_matrix.png)

### EXIF MetaData ile Ayırma

Her EXIF metadata özelliği için confidency matrix oluşturulur.

- Her bir _confidency matrix_ birbirinden bağımsız işlenir
- Tüm _confidency matrix_'lerin ortalaması alınır (_mean shift_)
- Her JPEG dosyası resmin kimlik verileri olan **EXIF Metadata** sahiptir
- Her frame'in metadata'larına bakılır ve farklılık söz konusu olursa resim değiştirilmiş demektir

![exif_data](res/exif_data.png)

## Error Level Analysis ile Ayırma

## Noise Analysis ile Ayırma

- Doğal resimler gürültülerle doludur
- Oynama yapıldığında gürültülerde belli olacak bir iz bırakırlar
- Airbrushing, Warps, Deforms, transformed clones yöntemleri ile değiştirilen resimleri bulamada avantaj sağlar

> Aclone detection ve ELA bazen bunları yaklayamayabilmekte.

> - [Buradaki](https://29a.ch/2015/08/21/noise-analysis-for-image-forensics) yazı faydalı olacaktır.
> - [Noise filtering in Digital Image Processing](https://medium.com/image-vision/noise-filtering-in-digital-image-processing-d12b5266847c)

## Code Kısmı

[Buradaki](https://github.com/minyoungg/selfconsistency/blob/master/demo.ipynb) kod incelenerek model bulunacak.

- `exif_demo` metodu tüm işlemini gerçekleştiği yer.

## Yapılacaklar

- [Buradaki](https://arxiv.org/pdf/1805.04096.pdf) paper'a devam edilecek
- [Demo kodundan](https://github.com/minyoungg/selfconsistency/blob/master/demo.ipynb) kaynak kodu anlaşılmaya çalışılacak
- Confidency matrix oluşturmaya bakılacak
- Affinity matrix'in detaylarına bakılacak

## Ek Bağlantılar

- [Image forgery detection](https://towardsdatascience.com/image-forgery-detection-2ee6f1a65442)

## Referanslar

- [Makale (Paper)](https://arxiv.org/pdf/1805.04096.pdf)
- [Proje](https://github.com/minyoungg/selfconsistency)
- [Projenin web sitesi](https://minyoungg.github.io/selfconsistency/)
- [Veriseti](http://people.eecs.berkeley.edu/~owens/consistency/exif_final.zip)
- [Photoshop veri seti](https://minyoungg.github.io/selfconsistency/in_wild/in_wild.tar.gz)
- [Adobe AI Fotoşop Algılama](http://openaccess.thecvf.com/content_cvpr_2018/papers/Zhou_Learning_Rich_Features_CVPR_2018_paper.pdf)
