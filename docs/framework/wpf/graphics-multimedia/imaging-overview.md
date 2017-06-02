---
title: "Общие сведения об обработке изображений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "преобразование изображений"
  - "обрезка изображений"
  - "декодирование форматов изображения"
  - "отображение изображений"
  - "кодирование форматов изображения"
  - "декодирование форматов изображения"
  - "кодирование форматов изображений"
  - "метаданные изображений"
  - "изображения, сведения об изображениях"
  - "API обработки изображений"
  - "метаданные, изображения"
  - "рисование с помощью изображений"
  - "поворачивание изображений"
  - "растягивание изображений"
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
caps.latest.revision: 32
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 29
---
# Общие сведения об обработке изображений
Данный раздел представляет собой введение в [!INCLUDE[TLA#tla_wic](../../../../includes/tlasharptla-wic-md.md)].  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] позволяет разработчикам отображать, преобразовывать и форматировать изображения.  
  
   
  
<a name="_wpfImaging"></a>   
## Компонент WPF Imaging  
 [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] предоставляет значительные усовершенствования возможностей обработки изображений в [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)].  Функции работы с изображениями, например вывод растрового изображения или использование изображения в обычных элементах управления, были ранее реализованы в библиотеках [!INCLUDE[TLA#tla_gdi](../../../../includes/tlasharptla-gdi-md.md)] и [!INCLUDE[TLA#tla_gdiplus](../../../../includes/tlasharptla-gdiplus-md.md)].  Эти интерфейсы [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] предоставляют базовые возможности обработки изображений, но лишены таких функций, как поддержка расширяемости кодеков и изображений высокого качества.  Интерфейс [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] создан для преодоления недостатков [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] и [!INCLUDE[TLA2#tla_gdiplus](../../../../includes/tla2sharptla-gdiplus-md.md)] и предоставления нового набора [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] для отображения и использования изображений в приложениях.  
  
 Существует два способа доступа к [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] — управляемому компоненту и неуправляемому компоненту.  Неуправляемый компонент предоставляет следующие возможности.  
  
-   Расширяемость для новых или собственных форматов изображений.  
  
-   Улучшенная производительность и повышенный уровень безопасности для собственных форматов изображений, включая [!INCLUDE[TLA#tla_bmp](../../../../includes/tlasharptla-bmp-md.md)], [!INCLUDE[TLA#tla_jpegorg](../../../../includes/tlasharptla-jpegorg-md.md)], [!INCLUDE[TLA#tla_png](../../../../includes/tlasharptla-png-md.md)], [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)], [!INCLUDE[TLA#tla_wdp](../../../../includes/tlasharptla-wdp-md.md)], [!INCLUDE[TLA#tla_gif](../../../../includes/tlasharptla-gif-md.md)] и значки \(ICO\).  
  
-   Сохранение данных изображения с высокой глубиной цвета — до 8 бит на канал \(до 32 бит на пиксель\).  
  
-   Неразрушающее масштабирование, обрезка и повороты.  
  
-   Упрощенное управление цветом.  
  
-   Поддержка собственных метаданных в файле.  
  
-   Управляемый компонент использует неуправляемую инфраструктуру для предоставления плавной интеграции изображений с другими возможностями [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], например, [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], анимацией и графикой.  Управляемый компонент также использует преимущества модели расширяемости кодека для работы с изображениями [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)], которая позволяет автоматически распознавать новые форматы изображений в приложениях [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 Большинство управляемых [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] находятся в пространстве имен <xref:System.Windows.Media.Imaging?displayProperty=fullName>, несмотря на то что несколько важных типов, таких как <xref:System.Windows.Media.ImageBrush> и <xref:System.Windows.Media.ImageDrawing> находятся в пространстве имен <xref:System.Windows.Media?displayProperty=fullName>, а <xref:System.Windows.Controls.Image> находится в пространстве имен <xref:System.Windows.Controls?displayProperty=fullName>.  
  
 В этом разделе содержится дополнительная информация об управляемом компоненте.  Дополнительные сведения о неуправляемых интерфейсах [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] см. в документации к [Неуправляемому WPF\-компоненту для работы с изображениями](_wic_lh).  
  
<a name="_imageformats"></a>   
## Форматы изображений в WPF  
 Кодек используется для декодирования или кодирования определенного формата носителя.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] включает в себя кодек для [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)], [!INCLUDE[TLA2#tla_jpeg](../../../../includes/tla2sharptla-jpeg-md.md)], [!INCLUDE[TLA2#tla_png](../../../../includes/tla2sharptla-png-md.md)], [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], [!INCLUDE[TLA2#tla_wdp](../../../../includes/tla2sharptla-wdp-md.md)], [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] и форматов изображения ICON.  Каждый из этих кодеков позволяет приложениям декодировать и кодировать \(за исключением значков\) соответствующие им форматы изображений.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> является важным классом, используемым для декодирования и кодирования изображений.  Этот основной строительный блок конвейера [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] представляет отдельный, постоянный набор пикселей определенного размера и разрешения.  <xref:System.Windows.Media.Imaging.BitmapSource> может быть отдельным фреймом многокадрового изображения или результатом преобразования, выполненного с <xref:System.Windows.Media.Imaging.BitmapSource>.  Он является родителем многих основных классов, используемых при обработке изображений [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], таких как <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 <xref:System.Windows.Media.Imaging.BitmapFrame> используется для хранения растровых данных формата изображения.  Большинство форматов изображений поддерживают один <xref:System.Windows.Media.Imaging.BitmapFrame>, хотя форматы, такие как [!INCLUDE[TLA2#tla_gif](../../../../includes/tla2sharptla-gif-md.md)] и [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)], поддерживают несколько фреймов на изображение.  Фреймы используются декодерами в качестве входных данных и передаются кодировщикам для создания файлов изображений.  
  
 В следующем примере показано создание <xref:System.Windows.Media.Imaging.BitmapFrame> из <xref:System.Windows.Media.Imaging.BitmapSource> и добавление его к изображению [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)].  
  
 [!code-csharp[BitmapFrameExample#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### Декодирование форматов изображения  
 Декодирование изображений является преобразованием формата изображения в данные изображения, которые могут использоваться системой.  Затем данные изображения могут быть использованы для отображения, обработки или кодирования в другой формат.  Выбор декодера зависит от формата изображения.  Выбор кодека производится автоматически, если не указан определенный декодер.  В примерах раздела [Отображение изображений в WPF](#_displayingimages) показано автоматическое декодирование.  Декодеры пользовательских форматов, разработанные с помощью неуправляемых интерфейсов [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] и зарегистрированные в системе, автоматически участвуют в выборе декодера.  Поэтому пользовательские форматы могут автоматически отображаться в приложениях [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
 В следующем примере показано использование декодера точечных рисунков для декодирования формата изображения [!INCLUDE[TLA2#tla_bmp](../../../../includes/tla2sharptla-bmp-md.md)].  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### Кодирование формата изображения  
 Кодирование изображения является преобразованием данных изображения в определенный формат изображения.  Закодированные данные изображения могут затем использоваться для создания новых файлов изображения.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] предоставляет кодировщики для каждого из описанных выше форматов изображения.  
  
 В следующем примере показано использование кодировщика для сохранения вновь созданного точечного рисунка.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## Отображение изображений в WPF  
 Существует несколько способов отображения изображений в приложениях [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)].  Изображения могут быть отображены с помощью элемента управления <xref:System.Windows.Controls.Image>, нарисованы на визуальном объекте с помощью <xref:System.Windows.Media.ImageBrush> или начерчены с использованием <xref:System.Windows.Media.ImageDrawing>.  
  
### Использование элемента управления Image  
 <xref:System.Windows.Controls.Image> — это элемент Framework, который является основным способом отображения рисунков в приложениях.  В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] существует два способа использования <xref:System.Windows.Controls.Image>: в синтаксисе атрибута или свойства.  В следующем примере показано отображение изображения шириной в 200 пикселей с помощью как синтаксиса атрибута, так и синтаксиса тега свойства.  Дополнительные сведения о синтаксисе атрибута и синтаксисе свойства см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
 [!code-xml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Многие примеры используют объект <xref:System.Windows.Media.Imaging.BitmapImage> для ссылки на файл изображения.  <xref:System.Windows.Media.Imaging.BitmapImage> является специализированным <xref:System.Windows.Media.Imaging.BitmapSource>, улучшенным для загрузки [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], и представляет собой простой способ отображения изображений в качестве <xref:System.Windows.Controls.Image.Source%2A> элемента управления <xref:System.Windows.Controls.Image>.  
  
 В следующем примере показано, как отобразить изображение шириной 200 пикселей с помощью кода.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Imaging.BitmapImage> реализует интерфейс <xref:System.ComponentModel.ISupportInitialize> для оптимизации инициализации на нескольких свойствах.  Изменения свойств могут возникать только во время инициализации объекта.  Вызов <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> сигнализирует о том, что началась инициализация, а <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> — о том, что инициализация завершена.  После инициализации изменения свойств игнорируются.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### Вращение, преобразование и обрезка изображений  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] позволяет пользователям осуществлять преобразования изображений с помощью свойств <xref:System.Windows.Media.Imaging.BitmapImage> или с использованием дополнительных объектов <xref:System.Windows.Media.Imaging.BitmapSource>, таких как <xref:System.Windows.Media.Imaging.CroppedBitmap> или <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>.  Эти преобразования могут масштабировать или вращать изображение, изменять формат пикселей или обрезать изображение.  
  
 Вращения изображения осуществляются с помощью свойства <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> элемента <xref:System.Windows.Media.Imaging.BitmapImage>.  Вращения могут быть выполнены только с шагом 90 градусов.  В следующем примере изображение повернуто на 90 градусов.  
  
 [!code-xml[ImageElementExample#TransformedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Преобразование изображения к различным форматам пикселей, например, к оттенкам серого, выполняется с помощью <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>.  В следующих примерах изображение преобразуется в <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xml[ImageElementExample_snip#ConvertedXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Чтобы обрезать изображение, можно использовать либо свойство <xref:System.Windows.UIElement.Clip%2A> элемента <xref:System.Windows.Controls.Image>, либо <xref:System.Windows.Media.Imaging.CroppedBitmap>.  Как правило, если требуется отобразить лишь часть изображения, то следует использовать <xref:System.Windows.UIElement.Clip%2A>.  Если требуется закодировать и сохранить обрезанное изображения, то следует использовать <xref:System.Windows.Media.Imaging.CroppedBitmap>.  В следующем примере изображение обрезается с помощью свойства Clip, использующего <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xml[ImageElementExample_snip#CroppedXAMLUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### Растягивание изображений  
 Свойство <xref:System.Windows.Controls.Image.Stretch%2A> управляет растягиванием изображения для заполнения его контейнера.  Свойство <xref:System.Windows.Controls.Image.Stretch%2A> принимает следующие значения, определенные перечислением <xref:System.Windows.Media.Stretch>:  
  
-   <xref:System.Windows.Media.Stretch>: изображение не растягивается для заполнения выходной области.  Если изображение больше, чем выходная область, то оно отображается в выходной области, при этом все, что не поместилось, отсекается.  
  
-   <xref:System.Windows.Media.Stretch>: изображение масштабируется по размеру выходной области.  Поскольку высота и ширина изображения масштабируются независимо друг от друга, исходные пропорции изображения могут не сохраниться.  Это означает, что изображение может деформироваться, чтобы полностью заполнить выходной контейнер.  
  
-   <xref:System.Windows.Media.Stretch>: изображение масштабируется так, чтобы полностью помещаться в выходной области.  При этом пропорции изображения сохраняются.  
  
-   <xref:System.Windows.Media.Stretch>: изображение масштабируется таким образом, чтобы оно полностью заполняло выходную область. При этом сохраняются исходные пропорции изображения.  
  
 В следующем примере к <xref:System.Windows.Controls.Image> применяется каждое из доступных перечислений <xref:System.Windows.Media.Stretch>.  
  
 На следующем рисунке показан результат примера и влияние различных параметров <xref:System.Windows.Controls.Image.Stretch%2A>, примененных к изображению.  
  
 ![Различные параметры растяжения TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/img-mmgraphics-stretchenum.png "img\_mmgraphics\_stretchenum")  
Различные параметры растяжения  
  
 [!code-xml[ImageElementExample_snip#ImageStretchExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### Рисование с помощью изображений  
 Изображения в приложении также могут быть нарисованы с помощью <xref:System.Windows.Media.Brush>.  Кисти позволяют рисовать от простых одноцветных объектов [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] до объектов со сложными наборами шаблонов и изображений.  Для рисования с помощью изображений следует использовать <xref:System.Windows.Media.ImageBrush>.  <xref:System.Windows.Media.ImageBrush> является типом <xref:System.Windows.Media.TileBrush>, определяющим его содержимое как точечный рисунок.  <xref:System.Windows.Media.ImageBrush> отображает одно изображение, которое задается его свойством <xref:System.Windows.Media.ImageBrush.ImageSource%2A>.  Можно управлять растяжением, выравниванием и мозаичным заполнением изображения, что позволяет избегать искажений и создавать шаблоны и другие эффекты.  На следующем рисунке показаны некоторые эффекты, которых можно добиться с помощью <xref:System.Windows.Media.ImageBrush>.  
  
 ![Примеры вывода ImageBrush](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-mmgraphics-imagebrushexamples.png "wcpsdk\_mmgraphics\_imagebrushexamples")  
Кисти изображений могут закрашивать фигуры, элементы управления, текст и т.д.  
  
 В следующем примере показано, как использовать изображение в качестве фона кнопки с помощью <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xml[UsingImageBrush#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> и рисовании с помощью изображений см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## Метаданные изображений  
 Некоторые файлы изображений содержат метаданные, описывающие содержимое или характеристики файла.  Например, большинство цифровых фотокамер создают изображения, содержащие метаданные об изготовителе и модели камеры, использованной для съемки изображения.  Каждый формат изображения обрабатывает метаданные по\-своему, но [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] предоставляет универсальный способ хранения и извлечения метаданных для каждого поддерживаемого формата изображения.  
  
 Доступ к метаданным предоставляется при помощи свойства <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> объекта <xref:System.Windows.Media.Imaging.BitmapSource>.  <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> возвращает объект <xref:System.Windows.Media.Imaging.BitmapMetadata>, который включает в себя все метаданные, содержащиеся в изображении.  Эти данные могут быть заключены в одной схеме метаданных или в комбинации различных схем.  [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] поддерживает следующие схемы метаданных изображения: [!INCLUDE[TLA#tla_exif](../../../../includes/tlasharptla-exif-md.md)], tEXt \(PNG Textual Data\), [!INCLUDE[TLA#tla_ifd](../../../../includes/tlasharptla-ifd-md.md)], [!INCLUDE[TLA#tla_iptc](../../../../includes/tlasharptla-iptc-md.md)] и [!INCLUDE[TLA#tla_xmp](../../../../includes/tlasharptla-xmp-md.md)].  
  
 Для упрощения процесса чтения метаданных <xref:System.Windows.Media.Imaging.BitmapMetadata> предоставляет несколько именованных свойств, к которым можно легко получить доступ, например, <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A> и <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>.  Многие из этих именованных свойств могут также использоваться для записи метаданных.  Дополнительная поддержка чтения метаданных обеспечивается считывателем запросов метаданных.  Метод <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> используется для извлечения считывателя запросов метаданных с помощью строки запроса, например *"\/app1\/exif\/"*.  В следующем примере <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> используется для получения текста, хранящегося в расположении *"\/Text\/Description"*.  
  
 [!code-cpp[BitmapMetadata#GetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Для написания метаданных используется запрос метаданных.  <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> получает запрос и задает желаемое значение.  В следующем примере <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> используется для записи текста, хранящегося в расположении *"\/Text\/Description"*.  
  
 [!code-cpp[BitmapMetadata#SetQuery](../../../../samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## Расширяемость кодека  
 Основной возможностью [!INCLUDE[TLA2#tla_wic](../../../../includes/tla2sharptla-wic-md.md)] является модель расширяемости для новых кодеков изображений.  Эти неуправляемые интерфейсы позволяют разработчикам кодеков интегрировать кодеки с [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], чтобы автоматически использовать в приложениях [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] новые форматы изображений.  
  
 Для примера расширяемости [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] см. раздел [Win32 Sample Codec](http://go.microsoft.com/fwlink/?LinkID=160052).  В этом примере показано создание декодера и кодировщика пользовательского формата изображения.  
  
> [!NOTE]
>  Для распознавания кодека системой он должен иметь цифровую подпись.  
  
## См. также  
 <xref:System.Windows.Media.Imaging.BitmapSource>   
 <xref:System.Windows.Media.Imaging.BitmapImage>   
 <xref:System.Windows.Controls.Image>   
 <xref:System.Windows.Media.Imaging.BitmapMetadata>   
 [двумерная графика и изображения](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Win32 Sample Codec](http://go.microsoft.com/fwlink/?LinkID=160052)