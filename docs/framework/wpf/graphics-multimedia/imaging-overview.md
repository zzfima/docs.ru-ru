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
ms.openlocfilehash: 3365c35e3e7b7fe5c0be48a65d7a14da0882c90e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186695"
---
# <a name="imaging-overview"></a>Общие сведения об обработке изображений
Эта тема содержит введение в Microsoft Windows Презентация Фонд Imaging компонента. WPF Imaging позволяет разработчикам отображать, преобразовывать и форматировать изображения.  

## <a name="wpf-imaging-component"></a>Компонент обработки изображений WPF  
 WPF Imaging обеспечивает значительные усовершенствования в возможностях визуализации в Microsoft Windows. Возможности визуализации, такие как отображение битовой карты или использование изображения на общем элементе управления, ранее зависели от интерфейса microsoft Windows Graphics Device Interface (GDI) или библиотек Microsoft Windows GDI. Эти API обеспечивают базовую функциональность изображений, но не имеют таких функций, как поддержка расширяемости кодека и высокая точность поддержки изображения. WPF Imaging предназначен для преодоления недостатков GDI и GDI и предоставления нового набора API для отображения и использования изображений в приложениях.  
  
 Существует два способа доступа к API wPF Imaging, управляемому компоненту и неуправляемому компоненту. Неуправляемый компонент предоставляет следующие возможности.  
  
- Модель расширяемости для новых или собственных форматов изображений.  
  
- Улучшенная производительность и безопасность на родных форматах изображений, включая bitmap (BMP), Совместная группа экспертов по фотографике (JPEG), Портативная сетевая графика (PNG), Формат файла с тегами (TIFF), Microsoft Windows Media Photo, Формат обмена графикой (GIF), и значок (.ico).  
  
- Сохранение изображений с большой глубиной цвета — до 8 бит на канал (32 бита на пиксель).  
  
- Неразрушающее масштабирование, обрезка и повороты.  
  
- Упрощенное управление цветом.  
  
- Поддержка собственных метаданных в файле.  
  
- Управляемый компонент использует неуправляемую инфраструктуру для обеспечения бесшовной интеграции изображений с другими функциями WPF, такими как [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]анимация и графика. Управляемый компонент также выигрывает от модели расширяемости кодеков для визуализации Windows Foundation (WPF), которая позволяет автоматически опознавать новые форматы изображений в приложениях WPF.  
  
 Большинство управляемых API изображений WPF <xref:System.Windows.Media.Imaging?displayProperty=nameWithType> находятся в пространстве имен, <xref:System.Windows.Media.ImageBrush> хотя <xref:System.Windows.Media.ImageDrawing> несколько <xref:System.Windows.Media?displayProperty=nameWithType> важных <xref:System.Windows.Controls.Image> типов, таких <xref:System.Windows.Controls?displayProperty=nameWithType> как и проживающие в пространстве имен и находятся в пространстве имен.  
  
 В этом разделе содержатся дополнительные сведения об управляемом компоненте. Для получения дополнительной информации о [Unmanaged WPF Imaging Component](/windows/desktop/wic/-wic-lh) неуправляемом API см.  
  
<a name="_imageformats"></a>
## <a name="wpf-image-formats"></a>Форматы изображений в WPF  

 Для кодирования и декодирования конкретного формата мультимедиа используются кодеки. WPF Imaging включает в себя кодек для форматов BMP, JPEG, PNG, TIFF, Windows Media Photo, GIF и ICON. Каждый из этих кодеков позволяет приложениям декодировать и, за исключением формата ICON, кодировать изображения соответствующих форматов.  
  
 <xref:System.Windows.Media.Imaging.BitmapSource>является важным классом, используемым в расшифровке и кодировании изображений. Это основной строительный блок конвейера WPF Imaging и представляет собой единый, постоянный набор пикселей при определенном размере и разрешении. A <xref:System.Windows.Media.Imaging.BitmapSource> может быть индивидуальным кадром изображения нескольких кадров, или это может <xref:System.Windows.Media.Imaging.BitmapSource>быть результатом преобразования, выполненного на . Это родитель многих начальных классов, используемых в <xref:System.Windows.Media.Imaging.BitmapFrame>изображении WPF, таких как .  
  
 A <xref:System.Windows.Media.Imaging.BitmapFrame> используется для хранения фактических данных битовой карты формата изображения. Многие форматы изображений <xref:System.Windows.Media.Imaging.BitmapFrame>поддерживают только одно изображение, хотя такие форматы, как GIF и TIFF, поддерживают несколько кадров на одно изображение. Кадры используются декодерами в качестве входных данных и передаются кодировщикам для создания файлов изображений.  
  
 Следующий пример показывает, <xref:System.Windows.Media.Imaging.BitmapFrame> как создается образ, <xref:System.Windows.Media.Imaging.BitmapSource> а затем добавляется к изображению TIFF.  
  
 [!code-csharp[BitmapFrameExample#10](~/samples/snippets/csharp/VS_Snippets_Wpf/BitmapFrameExample/CSharp/BitmapFrame.cs#10)]
 [!code-vb[BitmapFrameExample#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitmapFrameExample/VB/BitmapFrame.vb#10)]  
  
### <a name="image-format-decoding"></a>Декодирование изображений разных форматов  
 Декодирование изображения — это преобразование изображения в некотором формате в данные изображения, которые могут быть использованы системой. Данные изображения затем могут использоваться для отображения, обработки или кодирования в другой формат. Выбор декодера зависит от формата изображения. Выбор кодека производится автоматически, если не указан определенный декодер. Примеры в разделе [Отображение изображений в WPF](#_displayingimages) демонстрируют автоматическое декодирование. Декодеры пользовательских форматов, разработанные с использованием неуправляемых интерфейсов WPF Imaging и зарегистрированные в системе, автоматически участвуют в выборе декодера. Это позволяет автоматически отображать пользовательские форматы в приложениях WPF.  
  
 Следующий пример демонстрирует использование декодера битовой карты для декодирования изображения формата БМП.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
### <a name="image-format-encoding"></a>Кодирование изображений разных форматов  
 Кодирование изображения — это преобразование данных изображения в определенный формат. Кодированные данные изображения могут затем быть использованы для создания новых файлов изображений. WPF Imaging предоставляет кодеры для каждого из описанных выше форматов изображений.  
  
 В следующем примере показано использование кодировщика для сохранения вновь созданного точечного рисунка.  
  
 [!code-cpp[BmpBitmapDecoderEncoder#3](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#3)]
 [!code-csharp[BmpBitmapDecoderEncoder#3](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#3)]
 [!code-vb[BmpBitmapDecoderEncoder#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#3)]  
  
<a name="_displayingimages"></a>
## <a name="displaying-images-in-wpf"></a>Отображение изображений в WPF  
 Существует несколько способов отображения изображения в приложении Windows Presentation Foundation (WPF). Изображения могут отображаться <xref:System.Windows.Controls.Image> с помощью элемента <xref:System.Windows.Media.ImageBrush>управления, нарисованы на визуальном с помощью, или нарисованы с помощью <xref:System.Windows.Media.ImageDrawing>.  
  
### <a name="using-the-image-control"></a>Использование элемента управления Image  
 <xref:System.Windows.Controls.Image>является элементом фреймворка и основным способом отображения изображений в приложениях. В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] <xref:System.Windows.Controls.Image> , может быть использован в двух направлениях; атрибут синтаксиса или имущественного синтаксиса. В следующем примере показано, как можно отобразить изображение размером 200 пикселей в ширину, используя синтаксис атрибута и синтаксис тега свойства. Дополнительные сведения о синтаксисе атрибутов и синтаксисе свойства см. в разделе [Общие сведения о свойствах зависимостей](../advanced/dependency-properties-overview.md).  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
 Во многих примерах <xref:System.Windows.Media.Imaging.BitmapImage> используется объект для ссылки на файл изображений. <xref:System.Windows.Media.Imaging.BitmapImage>является <xref:System.Windows.Media.Imaging.BitmapSource> специализированным, который [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] оптимизирован для загрузки и <xref:System.Windows.Controls.Image.Source%2A> является <xref:System.Windows.Controls.Image> простым способом отображения изображений в качестве элемента управления.  
  
 В следующем примере показано, как построить изображение шириной 200 пикселей с использованием кода.  
  
> [!NOTE]
> <xref:System.Windows.Media.Imaging.BitmapImage>реализует <xref:System.ComponentModel.ISupportInitialize> интерфейс для оптимизации инициализации нескольких свойств. Изменения свойств происходят только во время инициализации объекта. Призыв <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> к сигналу о <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> том, что инициализация уже началась, и сигнализировать о завершении инициализации. После инициализации изменения свойств игнорируются.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
#### <a name="rotating-converting-and-cropping-images"></a>Вращение, преобразование и обрезка изображений  
 WPF позволяет пользователям преобразовывать <xref:System.Windows.Media.Imaging.BitmapImage> изображения с <xref:System.Windows.Media.Imaging.BitmapSource> помощью <xref:System.Windows.Media.Imaging.CroppedBitmap> <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>свойств или с помощью дополнительных объектов, таких как или . С помощью этих преобразований можно масштабировать или поворачивать изображения, изменять формат пикселей изображения и обрезать изображения.  
  
 Вращения изображений <xref:System.Windows.Media.Imaging.BitmapImage>выполняются <xref:System.Windows.Media.Imaging.BitmapImage.Rotation%2A> с использованием свойства . Вращение возможно только с шагом 90 градусов. В следующем примере изображение поворачивается на 90 градусов.  
  
 [!code-xaml[ImageElementExample#TransformedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml#transformedxaml2)]  
  
 [!code-csharp[ImageElementExample#TransformedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/TransformedImageExample.xaml.cs#transformedcsharp1)]
 [!code-vb[ImageElementExample#TransformedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/TransformedImageExample.xaml.vb#transformedcsharp1)]  
  
 Преобразование изображения в другой формат пикселей, <xref:System.Windows.Media.Imaging.FormatConvertedBitmap>такой как серая шкала, осуществляется с помощью. В следующих примерах изображение <xref:System.Windows.Media.PixelFormats.Gray4%2A>преобразуется в .  
  
 [!code-xaml[ImageElementExample_snip#ConvertedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml#convertedxaml2)]  
  
 [!code-csharp[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/FormatConvertedExample.xaml.cs#convertedcsharp1)]
 [!code-vb[ImageElementExample_snip#ConvertedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/FormatConvertedExample.xaml.vb#convertedcsharp1)]  
  
 Для обрезки изображения, <xref:System.Windows.UIElement.Clip%2A> либо <xref:System.Windows.Controls.Image> <xref:System.Windows.Media.Imaging.CroppedBitmap> свойство или могут быть использованы. Как правило, если вы просто хотите отобразить часть изображения, <xref:System.Windows.UIElement.Clip%2A> должны быть использованы. Если вам нужно кодировать и сохранить обрезанное <xref:System.Windows.Media.Imaging.CroppedBitmap> изображение, следует использовать его. В следующем примере изображение обрезается с помощью свойства клипа с помощью <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[ImageElementExample_snip#CroppedXAMLUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml#croppedxamlusingclip1)]  
  
 [!code-csharp[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/CroppedImageExample.xaml.cs#croppedcsharpusingclip1)]
 [!code-vb[ImageElementExample_snip#CroppedCSharpUsingClip1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/CroppedImageExample.xaml.vb#croppedcsharpusingclip1)]  
  
#### <a name="stretching-images"></a>Растягивание изображений  
 Свойство <xref:System.Windows.Controls.Image.Stretch%2A> контролирует, как изображение растягивается, чтобы заполнить его контейнер. Свойство <xref:System.Windows.Controls.Image.Stretch%2A> принимает следующие значения, определяемые перечислением: <xref:System.Windows.Media.Stretch>  
  
- <xref:System.Windows.Media.Stretch.None>: Изображение не растягивается, чтобы заполнить область вывода. Если изображение больше, чем область вывода, изображение заполняет область вывода с обрезкой тех частей, которые не входят.  
  
- <xref:System.Windows.Media.Stretch.Fill>: Изображение масштабируется в соответствии с областью вывода. Так как высота и ширина изображения масштабируются независимо друг от друга, исходные пропорции изображения могут не сохраниться. То есть изображение может быть деформировано для полного заполнения контейнера вывода.  
  
- <xref:System.Windows.Media.Stretch.Uniform>: Изображение масштабируется таким образом, что оно полностью вписывается в область вывода. Пропорции изображения сохраняются.  
  
- <xref:System.Windows.Media.Stretch.UniformToFill>: Изображение масштабируется таким образом, что оно полностью заполняет область вывода, сохраняя при этом исходное соотношение сторон изображения.  
  
 Следующий пример применяется каждый из доступных <xref:System.Windows.Media.Stretch> <xref:System.Windows.Controls.Image>перечислений к .  
  
 Следующее изображение показывает вывод из примера и <xref:System.Windows.Controls.Image.Stretch%2A> демонстрирует влияние различных параметров, которые имеют при применении к изображению.  
  
 ![Различные параметры растяжения TileBrush](./media/img-mmgraphics-stretchenum.jpg "img_mmgraphics_stretchenum")  
Различные параметры растяжения  
  
 [!code-xaml[ImageElementExample_snip#ImageStretchExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageStretchExample.xaml#imagestretchexamplewholepage)]  
  
### <a name="painting-with-images"></a>Закрашивание с помощью изображений  
 Изображения также могут отображаться в приложении, рисуя <xref:System.Windows.Media.Brush>с . Кисти позволяют заполнять объекты [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] различными изображениями, начиная с просто сплошного цвета и заканчивая сложными наборами шаблонов и изображений. Чтобы рисовать с <xref:System.Windows.Media.ImageBrush>изображениями, используйте . A <xref:System.Windows.Media.ImageBrush> — это <xref:System.Windows.Media.TileBrush> тип, определяющий его содержимое как изображение биткарты. Отображаетодно <xref:System.Windows.Media.ImageBrush> одно изображение, которое определяется его <xref:System.Windows.Media.ImageBrush.ImageSource%2A> свойством. Способом растяжения изображения, выравнивания и заполнения мозаикой можно управлять, что позволяет избегать искажений, создавать шаблоны и применять другие эффекты. Ниже приведены иллюстрации показаны некоторые <xref:System.Windows.Media.ImageBrush>эффекты, которые могут быть достигнуты с .  
  
 ![Примеры вывода ImageBrush](./media/wcpsdk-mmgraphics-imagebrushexamples.gif "wcpsdk_mmgraphics_imagebrushexamples")  
Используя кисти изображения, можно заполнять фигуры, элементы управления, текст и многое другое  
  
 Следующий пример показывает, как нарисовать фон кнопки <xref:System.Windows.Media.ImageBrush>с изображением с помощью .  
  
 [!code-xaml[UsingImageBrush#4](~/samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush/CS/PaintingWithImages.xaml#4)]  
  
 Для получения <xref:System.Windows.Media.ImageBrush> дополнительной информации и живописи изображения см [Картина с изображениями, рисунки и визуальные эффекты](painting-with-images-drawings-and-visuals.md).  
  
<a name="_metadata"></a>
## <a name="image-metadata"></a>Метаданные изображений  
 Некоторые файлы изображений содержат метаданные, описывающие содержимое или характеристики файла. Например, большинство цифровых фотоаппаратов создают изображения, содержащие метаданные об изготовителе и модели фотоаппарата, использованного для создания изображения. Каждый формат изображения обрабатывает метаданные по-разному, но WPF Imaging предоставляет единый способ хранения и извлечения метаданных для каждого поддерживаемого формата изображения.  
  
 Доступ к метаданным обеспечивается <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A> через <xref:System.Windows.Media.Imaging.BitmapSource> свойство объекта. <xref:System.Windows.Media.Imaging.BitmapSource.Metadata%2A>возвращает <xref:System.Windows.Media.Imaging.BitmapMetadata> объект, включающий все метаданные, содержащиеся на изображении. Эти данные могут представлять собой одну схему метаданных или комбинацию различных схем. WPF Imaging поддерживает следующие схемы метаданных изображений: обмениваемый файл изображений (Exif), tEXt (PNG текстовые данные), каталог файлов изображений (IFD), Международный совет по телекоммуникациям прессы (IPTC) и Расширяемая платформа метаданных (XMP).  
  
 Для того, чтобы упростить процесс <xref:System.Windows.Media.Imaging.BitmapMetadata> чтения метаданных, предоставляет несколько <xref:System.Windows.Media.Imaging.BitmapMetadata.Author%2A>названных свойств, которые могут быть легко доступны, такие как , <xref:System.Windows.Media.Imaging.BitmapMetadata.Title%2A>и <xref:System.Windows.Media.Imaging.BitmapMetadata.CameraModel%2A>. Многие из этих именованных свойств могут также использоваться для записи метаданных. Дополнительная поддержка чтения метаданных обеспечивается благодаря использованию считывателя запросов метаданных. Метод <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> используется для извлечения считывателя запросов метаданных, предоставляя строку запроса, такой как *"/app1/exif/"*. В следующем примере используется для получения текста, <xref:System.Windows.Media.Imaging.BitmapMetadata.GetQuery%2A> хранящегося в месте *"/Текст/описание".*  
  
 [!code-cpp[BitmapMetadata#GetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#getquery)]
 [!code-csharp[BitmapMetadata#GetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#getquery)]
 [!code-vb[BitmapMetadata#GetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#getquery)]  
  
 Для написания метаданных используется мастер написания запросов метаданных. <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A>получает автор запроса и устанавливает желаемое значение. В следующем примере используется для записи текста, <xref:System.Windows.Media.Imaging.BitmapMetadata.SetQuery%2A> хранящегося в месте *"/Текст/описание".*  
  
 [!code-cpp[BitmapMetadata#SetQuery](~/samples/snippets/cpp/VS_Snippets_Wpf/BitMapMetadata/CPP/BitmapMetadata.cpp#setquery)]
 [!code-csharp[BitmapMetadata#SetQuery](~/samples/snippets/csharp/VS_Snippets_Wpf/BitMapMetadata/CSharp/BitmapMetadata.cs#setquery)]
 [!code-vb[BitmapMetadata#SetQuery](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BitMapMetadata/VB/BitmapMetadata.vb#setquery)]  
  
<a name="_extensibility"></a>
## <a name="codec-extensibility"></a>Расширяемость кодеков  
 Основной особенностью WPF Imaging является модель расширяемости для новых кодеков изображений. Эти неуправляемые интерфейсы позволяют разработчикам кодеков интегрировать кодеки с WPF, чтобы новые форматы изображений могли автоматически использоваться приложениями WPF.  
  
 Для примера API для расширяемости см. [Win32 Sample Codec](https://go.microsoft.com/fwlink/?LinkID=160052) В этом примере показано создание декодера и кодировщика для пользовательского формата изображения.  
  
> [!NOTE]
> Чтобы система могла распознать кодек, он должен иметь цифровую подпись.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Imaging.BitmapSource>
- <xref:System.Windows.Media.Imaging.BitmapImage>
- <xref:System.Windows.Controls.Image>
- <xref:System.Windows.Media.Imaging.BitmapMetadata>
- [Двумерная графика и изображения](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Пример кодека Win32](https://go.microsoft.com/fwlink/?LinkID=160052)
