# Intro

    Hi guys, thanks for coming to read this documentation. Hopefully this docs can help you to understand and give you more context about onion.
Onion is still in development phase and i tried to add more components/widgets as much as i can, so bear with me! If you guys wanna contribute to create some great components don't be hestitate to open PR into the repository or just open the discussion to discuss anything related to the components/widgets or anything else. I am very gratefull for your feedback, any suggestions are welcome.

Ok, so i just want to inform you why onion is separated between two main package that is `particle` and `atom`. Can you guess? The reason behind that is of course because in flutter all are widgets so we need to separate the widget as small as possible to have a great performance. So it is talking about composition right?

Then the ideas coming from chemical things, in our body there are million compositions like cells, organs, tissues, etc. and atom is the smallest one. Atom is conciest of some particles, so that's why i named the smallest part is `particle`. Then for the widget that conciest of some particles which is the smallest widget like OniText, OniImage, etc. that will be grouped into `Atom`, back to the chemical concept `Atom is conciest of some particles`.

# A. Particle

## OniText
> A widget that will provide you a text.

| Props         | Type           | Requirement  |       Default       |             Short description                                                                               |
| ------------- |:--------------:| ------------:| -------------------:| -----------------------------------------------------------------------------------------------------------:|
| text          | `String`       | required     | -                   | text that will be diplayed on the screen                                                                    |
| dna           | `TextDNA`      | optional     | `TextDNA.bodyM`     | style that will be applied to the text, including the size. M suffix at `bodyM` define the size of the text |
| textAlign     | `TextAlign?`   | optional     | -                   | alignment of the text                                                                                       |
| overflow      | `TextOverflow?`| optional     | -                   | behavior to handle your overflowing text                                                                    |
| color         | `Color?`       | optional     | -                   | text color                                                                                                  |
| maxLines      | `int?`         | optional     | -                   | max lines that you expect when the text is overflowing the container                                        |

### How to use

If you don't want to change any optional props then what you have to do is just set the text, so you can simply write like the below code.

```dart
import 'package:onion/particle/text/text.dart';

OniText(text: 'hi, onion here');
```

But if you want to change the color for example, so you can write like the below code.

```dart
import 'package:onion/particle/text/text.dart';

OniText(
    text: 'hi, onion here',
    color: ColorDNA.red,
);
```

`Notes:` the example is using `ColorDNA` (the color that only defined on the oni lib) to set the color, actually you can set the color using `Colors` that already provided by flutter though. Or if you are still confusing about `dna` then you can read [here](/?id=c-dna) for more context.

## OniButton
> A widget that will provide you a button with `OniLabel` inside the widget, so that you can add prefix or suffix icon depend or your needs.

| Props         | Type           | Requirement  |       Default       |             Short description                                                                                           |
| ------------- |:--------------:| ------------:| -------------------:| -----------------------------------------------------------------------------------------------------------------------:|
| label         | `String`       | required     | -                   | text that will be diplayed on the screen                                                                                |
| dna           | `ButtonDNA`    | optional     | `ButtonDNA.primaryL`| style that will be applied to the button, including the size. For more context about `dna` read [here](/?id=c-dna)      |
| color         | `Color?`       | optional     | -                   | button color                                                                                                            |

### How to use

```dart
import 'package:onion/particle/button/button.dart';

OniButton(
    label: 'hi, onion here',
    onPressed: () {
        // do something.
    },
);
```

## OniImage
> A widget that will provide you an image. The source could be either your local asset or from network.

| Props         | Type           | Requirement  |       Default       |             Short description                                                                                           |
| ------------- |:--------------:| ------------:| -------------------:| -----------------------------------------------------------------------------------------------------------------------:|
| source        | `String`       | required     | -                   | url or path image, depend on what kind of source, local or from internet                                                |
| dimension     | `Dimension`    | required     | -                   | dimension of the image, you can set the width & height                                                                  |
| color         | `Color?`       | optional     | -                   | the color that will be applied to the image                                                                             |
| fit           | `BoxFit?`      | optional     | -                   | image fitment behavior                                                                                                  |
| alignment     | `Alignment`    | optional     | `Aligment.Center`   | image alignment                                                                                                         |
| enableCache   | `bool`         | optional     | `true`              | use cache when the source is coming from the internet. you can disabled cache by set the option to `false`              |
| errorWidget   | `Widget`       | optional     | -                   | a widget that will be displayed once the image is being failed to load                                                  |

### How to use

```dart
import 'package:onion/particle/image/image.dart';

OniImage(
    source: 'asset/onion-ico.png',
    dimension: const Dimension(width: 24, height: 24),
);
```

</br>

# B. Atom

## OniLabel
> A widget that will provide you a text with optional prefix & suffix icon.

| Props         | Type           | Requirement  |       Default       |             Short description                                                                                           |
| ------------- |:--------------:| ------------:| -------------------:| -----------------------------------------------------------------------------------------------------------------------:|
| label         | `String`       | required     | -                   | text that will be diplayed on the screen                                                                                |
| dna           | `TextDNA`      | optional     | `TextDNA.bodyM`     | style that will be applied to the text, including the size. M suffix at `bodyM` define the size of the text             |
| textAlign     | `TextAlign?`   | optional     | -                   | alignment of the text                                                                                                   |
| overflow      | `TextOverflow?`| optional     | -                   | behavior to handle your overflowing text                                                                                |
| color         | `Color?`       | optional     | -                   | text color                                                                                                              |
| maxLines      | `int?`         | optional     | -                   | max lines that you expect when the text is overflowing the container                                                    |
| iconColor     | `Color?`       | optional     | -                   | color that will be applied to the icon, either prefix or suffix icon                                                    |
| prefixIcon    | `String?`      | optional     | -                   | icon that will be appear before the label. The source could be from asset or network                                    |
| suffixIcon    | `String?`      | optional     | -                   | icon that will be appear after the label. The source could be from asset or network                                     |
| iconSize      | `int?`         | optional     | -                   | size of icon                                                                                                            |
| addSpaceAround| `bool`         | optional     | `true`              | add a bit space between label and icon. if you don't expect any space around them, you can set this option to `false`.  |

### How to use

If you don't want to change any optional props then what you have to do is just set the text, so you can simply write like the below code.

```dart
import 'package:onion/atom/label/label.dart';

OniLabel(text: 'hi, onion here');
```

But if you want to change the optional props, then it should be the same thing just make sure that you are set the props in the constructor.

# C. Dna

## TextDNA
> A style that will be applied to the text, including the size.

| Dna           | fontSize | fontWeight        |       
| ------------- |:--------:| -----------------:|
| captionXS     | 10.0     | normal            |
| bodyS         | 12.0     | normal            |
| bodyM         | 14.0     | normal            |
| bodyL         | 16.0     | normal            |
| bodyXL        | 18.0     | normal            |
| headerS       | 12.0     | bold              |
| headerM       | 14.0     | bold              |
| headerL       | 16.0     | bold              |
| headerXL      | 18.0     | bold              |

That is the standard dna for onion lib. if you feels need to customize the dna, then it should be easy for you to do so like the below code.

```dart
import 'package:onion/atom/label/label.dart';

OniText(
    text: 'hi, onion here',
    // here, you can copy the dna then modify the values.
    dna: TextDNA.bodyS.copyWith(
        fontFamily: 'sans-serif',
        fontWeight: FontWeight.bold,
    ),
);
```

## ButtonDNA
> A style that will be applied to the button, including the size.

| Dna           | minWidth | minHeight     | color                                                                                 | borderColor |
| ------------- |:--------:| -------------:| ------------------------------------------------------------------------------------: | -           |
| primaryS      | 50       | 30            | ![#FF565E](https://via.placeholder.com/15/FF565E/000000?text=+) `ColorDNA.red`        | -           |
| primaryM      | 60       | 35            | ![#FF565E](https://via.placeholder.com/15/FF565E/000000?text=+) `ColorDNA.red`        | -           |
| primaryL      | 70       | 40            | ![#FF565E](https://via.placeholder.com/15/FF565E/000000?text=+) `ColorDNA.red`        | -           |
| secondaryS    | 50       | 30            | ![#e4e8f6](https://via.placeholder.com/15/e4e8f6/000000?text=+) `ColorDNA.light`      | -           |
| secondaryM    | 60       | 35            | ![#e4e8f6](https://via.placeholder.com/15/e4e8f6/000000?text=+) `ColorDNA.red`        | -           |
| secondaryL    | 70       | 40            | ![#e4e8f6](https://via.placeholder.com/15/e4e8f6/000000?text=+) `ColorDNA.red`        | -           |
| outlineS      | 50       | 30            | ![#000000](https://via.placeholder.com/15/000000/000000?text=+) `Colors.transparant`  |![#D7DBDD](https://via.placeholder.com/15/D7DBDD/000000?text=+) `ColorDNA.grey03`          |
| outlineM      | 60       | 35            | ![#000000](https://via.placeholder.com/15/000000/000000?text=+) `Colors.transparant`  |![#D7DBDD](https://via.placeholder.com/15/D7DBDD/000000?text=+) `ColorDNA.grey03`          |
| outlineL      | 70       | 40            | ![#000000](https://via.placeholder.com/15/000000/000000?text=+) `Colors.transparant`  |![#D7DBDD](https://via.placeholder.com/15/D7DBDD/000000?text=+) `ColorDNA.grey03`          |

That is the standard dna for onion lib. if you feels need to customize the dna, then it should be easy for you to do so like the below code.

```dart
import 'package:onion/atom/label/label.dart';

OniButton(
    label: 'hi, onion here',
    // here, you can copy the dna then modify the values.
    dna: ButtonDNA.primaryL.copyWith(
        color: ColorDNA.black,
        labelColor: ColorDNA.white,
    ),
    onPressed: () {
        // do something.
    },
);
```

## OSION - Oni's collection

This Privacy Policy explains how osion collects, uses, and protects any information that you provide when using our mobile application osion.

**Information We Do Not Collect**

- We do not collect any personal information or data from users of our mobile application.

**Usage Data**

- We do not collect any usage data or statistics from users of our mobile application.

**Cookies**

- We do not use cookies in our mobile application.

- Changes to This Privacy Policy

**Contact Us**

- If you have any questions or suggestions about our Privacy Policy, do not hesitate to contact us at yudaoktavian@gmail.com

We may update our Privacy Policy from time to time. Thus, you are advised to review this page periodically for any changes. We will notify you of any changes by posting the new Privacy Policy on this page. These changes are effective immediately after they are posted on this page.