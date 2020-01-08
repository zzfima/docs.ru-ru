---
title: Общие сведения об обработке изображений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- metadata [WPF], images
- displaying images [WPF]
- Imaging API [WPF]
- image metadata [WPF]
- converting images [WPF]
- encoding image formats [WPF]
- format decoding for images [WPF]
- painting with images [WPF]
- stretching images [WPF]
- images [WPF], about imaging
- format encoding for images [WPF]
- cropping images [WPF]
- decoding image formats [WPF]
- rotating images [WPF]
ms.assetid: 72aad87a-e6f3-4937-94cd-a18b7766e990
ms.openlocfilehash: a4151ff610c67ac762f0096c6a136f4475317782
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636644"
---
# <a name="imaging-overview"></a>Общие сведения об обработке изображений
В этом разделе приводятся общие сведения о компоненте работы с образами Microsoft Windows Presentation Foundation. Создание образов WPF позволяет разработчикам отображать, преобразовывать и форматировать изображения.  

## <a name="wpf-imaging-component"></a>Компонент обработки изображений WPF  
 Создание образов WPF предоставляет значительные улучшения возможностей работы с образами в Microsoft Windows. Возможности работы с образами, такие как отображение точечного рисунка или использование изображения в стандартном элементе управления, ранее были связаны с библиотеками Microsoft Windows интерфейс графических устройств (GDI) или Microsoft Windows GDI+. Эти API предоставляют базовые функции создания образов, но не имеют таких функций, как поддержка расширения кодека и поддержка изображений высокого качества. Создание образов WPF предназначено для преодоления недостатков GDI и GDI+ и предоставления нового набора API для вывода и использования изображений в приложениях.  
  
 Существует два способа доступа к API обработки изображений WPF — управляемому компоненту и неуправляемому компоненту. Неуправляемый компонент предоставляет следующие возможности.  
  
- Модель расширяемости для новых или собственных форматов изображений.  
  
- Улучшенная производительность и безопасность в собственных форматах образов, включая точечные рисунки (BMP), группу экспертов по работе с фотографами (JPEG), PNG, формат файлов изображений с тегами (TIFF), приложение Microsoft Windows Media Graphics, формат GIF, и (ICO).  
  
- Сохранение изображений с большой глубиной цвета — до 8 бит на канал (32 бита на пиксель).  
  
- Неразрушающее масштабирование, обрезка и повороты.  
  
- Упрощенное управление цветом.  
  
- Поддержка собственных метаданных в файле.  
  
- Управляемый компонент использует неуправляемую инфраструктуру для обеспечения беспрепятственной интеграции образов с другими функциями WPF, такими как [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], анимация и графика. Управляемый компонент также имеет преимущества от модели расширения кодека Windows Presentation Foundation (WPF) для создания образов, которая обеспечивает автоматическое распознавание новых форматов изображений в приложениях WPF.  
  
 Большая часть управляемого API для работы с образами WPF находится в пространстве имен <xref:System.Windows.Media.Imaging?displayProperty=nameWithType>, хотя несколько важных типов, таких как <xref:System.Windows.Media.ImageBrush> и <xref:System.Windows.Media.ImageDrawing>, находятся в пространстве имен <xref:System.Windows.Media?displayProperty=nameWithType> и <xref:System.Windows.Controls.Image> находятся в пространстве имен <xref:System.Windows.Controls?displayProperty=nameWithType>.  
  
 В этом разделе содержатся дополнительные сведения об управляемом компоненте. Дополнительные сведения о неуправляемом API см. в документации по [неуправляемым компонентам работы с образами WPF](/windows/desktop/wic/-wic-lh) .  
  
<a name="_imageformats"></a>   
## <a name="wpf-image-formats"></a>Форматы изображений в WPF  

 Для кодирования и декодирования конкретного формата мультимедиа используются кодеки. Изображения WPF включают кодек для форматов изображений BMP, JPEG, PNG, TIFF, Windows Media Photo, GIF и ICON. Каждый из этих кодеков позволяет приложениям декодировать и, за исключением формата ICON, кодировать изображения соответствующих форматов.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource> является важным классом, используемым при декодировании и кодировании образов. Это базовый Стандартный блок конвейера создания образов WPF, который представляет один постоянный набор пикселей с определенным размером и разрешением. <xref:System.Windows.Media.Imaging.BitmapSource> может быть отдельным кадром изображения в нескольких кадрах или результатом преобразования, выполненного в <xref:System.Windows.Media.Imaging.BitmapSource>. Он является родительским для многих основных классов, используемых в обработке изображений WPF, таких как <xref:System.Windows.Media.Imaging.BitmapFrame>.  
  
 <xref:System.Windows.Media.Imaging.BitmapFrame> используется для хранения данных с фактическим растровым изображением формата изображения. Многие форматы изображений поддерживают только один <xref:System.Windows.Media.Imaging.BitmapFrame>, хотя форматы, такие как GIF и TIFF, поддерживают несколько кадров на изображение. Кадры используются декодерами в качестве входных данных и передаются кодировщикам для создания файлов изображений.  
  
 В следующем примере показано, как <xref:System.Windows.Media.Imaging.BitmapFrame> создается из <xref:System.Windows.Media.Imaging.BitmapSource> и добавляется в изображение TIFF.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Декодирование изображений разных форматов  
 Декодирование изображения — это преобразование изображения в некотором формате в данные изображения, которые могут быть использованы системой. Данные изображения затем могут использоваться для отображения, обработки или кодирования в другой формат. Выбор декодера зависит от формата изображения. Выбор кодека производится автоматически, если не указан определенный декодер. Примеры в разделе [Отображение изображений в WPF](#_displayingimages) демонстрируют автоматическое декодирование. Декодеры пользовательских форматов, разработанные с помощью неуправляемых интерфейсов обработки изображений WPF и зарегистрированных в системе, автоматически участвуют в выборе декодера. Это позволяет автоматически отображать пользовательские форматы в приложениях WPF.  
  
 В следующем примере демонстрируется использование декодера точечных рисунков для декодирования изображения формата BMP.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Кодирование изображений разных форматов  
 Кодирование изображения — это преобразование данных изображения в определенный формат. Кодированные данные изображения могут затем быть использованы для создания новых файлов изображений. Изображения WPF предоставляют кодировщики для каждого из форматов изображений, описанных выше.  
  
 В следующем примере показано использование кодировщика для сохранения вновь созданного точечного рисунка.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>   
## <a name="displaying-images-in-wpf"></a>Отображение изображений в WPF  
 Существует несколько способов отобразить изображение в приложении Windows Presentation Foundation (WPF). Изображения могут отображаться с помощью элемента управления <xref:System.Windows.Controls.Image>, закрашены на визуальном элементе с помощью <xref:System.Windows.Media.ImageBrush>или нарисованы с помощью <xref:System.Windows.Media.ImageDrawing>.  
  
### <a name="using-the-image-control"></a>Использование элемента управления Image  
 <xref:System.Windows.Controls.Image> является элементом платформы и основным способом для вывода изображений в приложениях. В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]<xref:System.Windows.Controls.Image> можно использовать двумя способами. синтаксис атрибута или свойства. В следующем примере показано, как можно отобразить изображение размером 200 пикселей в ширину, используя синтаксис атрибута и синтаксис тега свойства. Дополнительные сведения о синтаксисе атрибутов и синтаксисе свойства см. в разделе [Общие сведения о свойствах зависимостей](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Во многих примерах для ссылки на файл изображения используется объект <xref:System.Windows.Media.Imaging.BitmapImage>. <xref:System.Windows.Media.Imaging.BitmapImage> — это специализированная <xref:System.Windows.Media.Imaging.BitmapSource>, оптимизированная для [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] загрузки и позволяющая легко отображать изображения как <xref:System.Windows.Controls.Image.Source%2A> элемента управления <xref:System.Windows.Controls.Image>.  
  
 В следующем примере показано, как построить изображение шириной 200 пикселей с использованием кода.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage> реализует интерфейс <xref:System.ComponentModel.ISupportInitialize> для оптимизации инициализации нескольких свойств. Изменения свойств происходят только во время инициализации объекта. Вызовите <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A>, чтобы сообщить, что инициализация началась и <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> сигнал о завершении инициализации. После инициализации изменения свойств игнорируются.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Вращение, преобразование и обрезка изображений  
 WPF позволяет пользователям преобразовывать изображения с помощью свойств <xref:System.Windows.Media.Imaging.BitmapImage> или с помощью дополнительных объектов <xref:System.Windows.Media.Imaging.BitmapSource>, таких как <xref:System.Windows.Media.Imaging.CroppedBitmap> или <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. С помощью этих преобразований можно масштабировать или поворачивать изображения, изменять формат пикселей изображения и обрезать изображения.  
  
 Поворот изображения выполняется с помощью свойства <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> <xref:System.Windows.Media.Imaging.BitmapImage>. Вращение возможно только с шагом 90 градусов. В следующем примере изображение поворачивается на 90 градусов.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Преобразование изображения в другой формат пикселей, например в градации серого, выполняется с помощью <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>. В следующих примерах изображение преобразуется в <xref:System.Windows.Media.PixelFormats.Gray4%2A>.  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Чтобы обрезать изображение, можно использовать либо свойство <xref:System.Windows.UIElement.Clip%2A> <xref:System.Windows.Controls.Image>, либо <xref:System.Windows.Media.Imaging.CroppedBitmap>. Как правило, если нужно просто отобразить часть изображения, следует использовать <xref:System.Windows.UIElement.Clip%2A>. Если необходимо закодировать и сохранить обрезанное изображение, следует использовать <xref:System.Windows.Media.Imaging.CroppedBitmap>. В следующем примере изображение обрезается с помощью свойства Clip с помощью <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Растягивание изображений  
 Свойство <xref:System.Windows.Controls.Image.Stretch%2A> определяет способ растяжения изображения для заполнения его контейнера. Свойство <xref:System.Windows.Controls.Image.Stretch%2A> принимает следующие значения, определяемые перечислением <xref:System.Windows.Media.Stretch>:  
  
- <xref:System.Windows.Media.Stretch.None>: изображение не растягивается для заполнения области вывода. Если изображение больше, чем область вывода, изображение заполняет область вывода с обрезкой тех частей, которые не входят.  
  
- <xref:System.Windows.Media.Stretch.Fill>: изображение масштабируется в соответствии с областью вывода. Так как высота и ширина изображения масштабируются независимо друг от друга, исходные пропорции изображения могут не сохраниться. То есть изображение может быть деформировано для полного заполнения контейнера вывода.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: изображение масштабируется таким образом, чтобы оно полностью поместилось в области вывода. Пропорции изображения сохраняются.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: изображение масштабируется таким образом, чтобы полностью заполнить область вывода с сохранением исходного пропорций изображения.  
  
 В следующем примере каждый из доступных перечислений <xref:System.Windows.Media.Stretch> применяется к <xref:System.Windows.Controls.Image>.  
  
 На следующем рисунке показаны выходные данные из примера и демонстрируется влияние различных параметров <xref:System.Windows.Controls.Image.Stretch%2A>, примененных к изображению.  
  
 ![Различные параметры растяжения TileBrush](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Различные параметры растяжения  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Закрашивание с помощью изображений  
 Изображения также могут отображаться в приложении путем рисования с помощью <xref:System.Windows.Media.Brush>. Кисти позволяют заполнять объекты [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] различными изображениями, начиная с просто сплошного цвета и заканчивая сложными наборами шаблонов и изображений. Для рисования с помощью изображений используйте <xref:System.Windows.Media.ImageBrush>. <xref:System.Windows.Media.ImageBrush> — это тип <xref:System.Windows.Media.TileBrush>, который определяет его содержимое в виде растрового изображения. <xref:System.Windows.Media.ImageBrush> отображает одно изображение, которое задается его свойством <xref:System.Windows.Media.ImageBrush.ImageSource%2A>. Способом растяжения изображения, выравнивания и заполнения мозаикой можно управлять, что позволяет избегать искажений, создавать шаблоны и применять другие эффекты. На следующем рисунке показаны некоторые эффекты, которые можно достигнуть с помощью <xref:System.Windows.Media.ImageBrush>.  
  
 ![Примеры вывода ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Используя кисти изображения, можно заполнять фигуры, элементы управления, текст и многое другое  
  
 В следующем примере показано, как закрасить фон кнопки с изображением с помощью <xref:System.Windows.Media.ImageBrush>.  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> и рисовании изображений см. [в статье Рисование с помощью изображений, рисунков и визуальных элементов](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>   
## <a name="image-metadata"></a>Метаданные изображений  
 Некоторые файлы изображений содержат метаданные, описывающие содержимое или характеристики файла. Например, большинство цифровых фотоаппаратов создают изображения, содержащие метаданные об изготовителе и модели фотоаппарата, использованного для создания изображения. Каждый формат изображения обрабатывает метаданные по-разному, но при работе с образами WPF обеспечивается единообразный способ хранения и извлечения метаданных для каждого поддерживаемого формата изображения.  
  
 Доступ к метаданным предоставляется через свойство <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> объекта <xref:System.Windows.Media.Imaging.BitmapSource>. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> возвращает объект <xref:System.Windows.Media.Imaging.BitmapMetadata>, содержащий все метаданные, содержащиеся в изображении. Эти данные могут представлять собой одну схему метаданных или комбинацию различных схем. Создание образов WPF поддерживает следующие схемы метаданных изображений: файл обмена изображениями (EXIF), текст (текстовые данные PNG), каталог файлов изображений (IFD), Международный совет по пресс-коммуникациям (IPTC) и расширяемую платформу метаданных (XMP).  
  
 Чтобы упростить процесс чтения метаданных, <xref:System.Windows.Media.Imaging.BitmapMetadata> предоставляет несколько именованных свойств, к которым можно легко получить доступ, например <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>, <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>и <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>. Многие из этих именованных свойств могут также использоваться для записи метаданных. Дополнительная поддержка чтения метаданных обеспечивается благодаря использованию считывателя запросов метаданных. Метод <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> используется для получения считывателя запросов метаданных путем предоставления строкового запроса, например *"/APP1/EXIF/"* . В следующем примере <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> используется для получения текста, хранящегося в расположении *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Для написания метаданных используется мастер написания запросов метаданных. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> получает модуль записи запроса и задает нужное значение. В следующем примере <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> используется для записи текста, хранящегося в расположении *"/Text/Description"* .  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>   
## <a name="codec-extensibility"></a>Расширяемость кодеков  
 Основной функцией работы с образами WPF является модель расширяемости для новых кодеков изображений. Эти неуправляемые интерфейсы позволяют разработчикам кодеков интегрировать кодеки в WPF, поэтому новые форматы изображений могут автоматически использоваться приложениями WPF.  
  
 Пример API расширяемости см. в [примере кодека Win32](https://go.microsoft.com/fwlink/?LinkID=160052). В этом примере показано создание декодера и кодировщика для пользовательского формата изображения.  
  
> [!NOTE]
> Чтобы система могла распознать кодек, он должен иметь цифровую подпись.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Пример кодека Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
