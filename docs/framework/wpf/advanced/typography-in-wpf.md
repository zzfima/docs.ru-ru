---
title: Типографская разметка
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 3d94873931e3ee6df780df214f508258aa07a791
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735531"
---
# <a name="typography-in-wpf"></a>Оформление в WPF
В этом разделе содержатся вводные сведения об основных типографических возможностях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Эти функции включают повышение качества и производительности отрисовки текста, поддержку типографских шрифтов OpenType, расширенный международный текст, расширенную поддержку шрифта и новые интерфейсы программирования текстовых приложений (API).  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Улучшенное качество и производительность работы с текстом  
 Текст в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается с помощью технологии Microsoft ClearType, что повышает четкость и удобочитаемость текста. Технология ClearType представляет собой программную технологию, разработанную корпорацией Майкрософт, которая повышает удобочитаемость текста на существующих LCDs (жидкокристаллических дисплеях), например экраны ноутбука, карманные экраны и мониторы с плоскими панелями. Технология ClearType использует отрисовку в виде вложенных точек, что позволяет отображать текст с большей точностью до своей реальной фигуры, выполняя символы в дробной части пикселя. Дополнительное разрешение повышает четкость мелких деталей отображаемого текста, значительно облегчая его длительное чтение. Еще одним улучшением технологии ClearType в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является сглаживание по оси y, которое сглаживает верхние и нижние границы мелких кривых в текстовых символах. Дополнительные сведения о функциях ClearType см. в разделе [Общие сведения о технологии](cleartype-overview.md)ClearType.  
  
 ![Текст со сглаживанием ClearType по оси Y](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Текст со сглаживанием ClearType по оси Y  
  
 Весь конвейер отрисовки текста может поддерживать аппаратное ускорение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], позволяя применять компьютер с минимальными требованиями к оборудованию. Отрисовка, которая не может быть выполнена на аппаратном уровне, использует программный рендеринг. Аппаратное ускорение влияет на все этапы конвейера отрисовки текста — от хранения отдельных глифов, совмещения глифов в выполнении глифов, применения эффектов к применению алгоритма смешения ClearType к окончательно отображаемым выходным данным. Дополнительные сведения об аппаратном ускорении см. в разделе [Уровни графической отрисовки](graphics-rendering-tiers.md).  
  
 ![Диаграмма конвейера отрисовки текста](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Кроме того, анимированный текст, независимо от того, состоит он их знаков или глифов, использует все преимущества возможностей графического оборудования, работающего под управлением [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Это приводит к сглаживанию текстовой анимации.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Типография с широкими возможностями  
 Формат шрифта OpenType является расширением формата шрифта TrueType®. Формат шрифтов OpenType был разработан совместно корпорацией Майкрософт и Adobe, а также предоставляет широкий спектр расширенных типографских функций. Объект <xref:System.Windows.Documents.Typography> предоставляет множество дополнительных возможностей шрифтов OpenType, таких как стилистические варианты и глифы. Windows SDK предоставляет набор образцов шрифтов OpenType, разработанных с широкими возможностями, такими как шрифты Pericles и Pescadero. Дополнительные сведения см. в разделе [Пакет образцов шрифтов OpenType](sample-opentype-font-pack.md).  
  
 Шрифт OpenType Pericles содержит дополнительные глифы, предоставляющие стилистические варианты для стандартного набора глифов. Приведенный ниже текст отображает глифы с изменением стиля.  
  
 ![Текст, использующий глифы с изменением стилей OpenType](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Текст, использующий глифы с изменением стилей OpenType")  
  
 Swash-глифы являются декоративными глифами, которые используют сложную орнаментацию, часто связанную с каллиграфией. Следующий текст отображает стандартные и swash-глифы для шрифта Pescadero.  
  
 ![Текст, использующий стандартные и swash-глифы OpenType](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Текст, использующий стандартные и swash глифы OpenType")  
  
 Дополнительные сведения о функциях OpenType см. в разделе [функции шрифтов OpenType](opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>   
## <a name="enhanced-international-text-support"></a>Расширенная многоязыковая поддержка текста  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает расширение международного текста, предоставляя следующие возможности.  
  
- Автоматическая расстановка пробелов во всех системах письма с использованием адаптивного измерения.  
  
- Широкая поддержка международного текста. Дополнительные сведения см. в разделе [Глобализация для WPF](globalization-for-wpf.md).  
  
- Управляемый языком разрыв строки, расстановка переносов и выравнивание.  
  
<a name="Enhanced_Font_Support"></a>   
## <a name="enhanced-font-support"></a>Расширенная поддержка шрифтов  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет расширенную поддержку шрифта с помощью следующих возможностей.  
  
- Юникод для всех текстов. Поведение шрифта и выбор, больше не требующий набора символов или кодовой страницы.  
  
- Поведение шрифта зависит от глобальных настроек, таких как язык системы.  
  
- Отдельные типы <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>и <xref:System.Windows.FontStyle> для определения <xref:System.Windows.Media.FontFamily>. Это обеспечивает большую гибкость, чем в программировании Win32, при котором для определения семейства шрифтов используются логические сочетания курсива и полужирного шрифта.  
  
- Направление письма (горизонтальное или вертикальное) обрабатывается в зависимости от имени шрифта.  
  
- Связывание шрифтов и откат шрифтов в переносимом XML-файле с использованием технологии составных шрифтов. Составные шрифты позволяют конструировать все шрифты многоязычного диапазона. Составные шрифты также предоставляют механизм, который позволяет избежать отображения отсутствующих глифов. Дополнительные сведения см. в комментариях в классе <xref:System.Windows.Media.FontFamily>.  
  
- Международные шрифты, созданные из составных шрифтов с использованием группы одноязыковых шрифтов. Это позволяет избежать затрат ресурсов при разработке шрифтов для нескольких языков.  
  
- Составные шрифты внедряются в документ, тем самым обеспечивая его совместимость. Дополнительные сведения см. в комментариях в классе <xref:System.Windows.Media.FontFamily>.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Новые API  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет разработчикам несколько текстовых интерфейсов для использования при включении текста в свои приложения. Эти API группируются по трем категориям:  
  
- **Макет и пользовательский интерфейс**. Общие элементы управления текстом для графического пользовательского интерфейса (GUI).  
  
- **Облегченное рисование текста**. Позволяет рисовать текст непосредственно в объектах.  
  
- **Дополнительное форматирование текста**. Позволяет реализовать пользовательский обработчик текста.  
  
### <a name="layout-and-user-interface"></a>Макет и пользовательский интерфейс  
 На самом верхнем уровне функциональности текстовые интерфейсы API предоставляют стандартные элементы управления [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], такие как <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>и <xref:System.Windows.Controls.TextBox>. Эти элементы управления предоставляют основные элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в приложении и способ представления текста и взаимодействия с ним. Такие элементы управления, как <xref:System.Windows.Controls.RichTextBox> и <xref:System.Windows.Controls.PasswordBox>, обеспечивают более расширенную или специализированную обработку текста. Классы, такие как <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>и <xref:System.Windows.Documents.TextPointer>, обеспечивают полезную обработку текста. Эти [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы управления предоставляют такие свойства, как <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>и <xref:System.Windows.Controls.Control.FontStyle%2A>, которые позволяют управлять шрифтом, используемым для отрисовки текста.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Использование эффектов точечных рисунков и текстовых эффектов  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет создавать визуально интересные применения текста, используя такие возможности, как эффекты точечных рисунков, преобразования и текстовые эффекты. В следующем примере показан типичный эффект тени, примененный к тексту.  
  
 ![Тень текста с мягкостью &#61; 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg) 
  
 В следующем примере показан эффект тени и шума, примененный к тексту.  
  
 ![Тень текста с шумом](./media/typography-in-wpf/drop-shadow-noise-text.jpg) 
  
 В следующем примере показан эффект внешнего свечения, примененный к тексту.  
  
 ![Тень текста с использованием OuterGlowBitmapEffect](./media/typography-in-wpf/text-shadow-glow-effect.jpg)
  
 В следующем примере показан эффект размытия, примененный к тексту.  
  
 ![Тень текста с использованием BlurBitmapEffect](./media/typography-in-wpf/text-shadow-blur-effect.jpg)  

 В следующем примере показаны вторая строка текста, масштабированная на 150 % вдоль оси X, и третья строка текста, масштабированная на 150 % вдоль оси Y.  
  
 ![Текст, масштабируемый с использованием ScaleTransform](./media/typography-in-wpf/scaled-text-scaletransform.jpg) 
  
 В следующем примере показан текст, наклоненный вдоль оси X.  
  
 ![Текст, искаженный с использованием SkewTransform](./media/typography-in-wpf/skewed-transformed-text.jpg)
  
 Объект <xref:System.Windows.Media.TextEffect> — это вспомогательный объект, который позволяет обрабатывать текст как одну или несколько групп символов в текстовой строке. В следующем примере показан поворот отдельных символов. Поворот каждого символа осуществляется независимо от других с интервалом в 1 секунду.  
  
 ![Снимок экрана текстового эффекта: повернутый текст](./media/typography-in-wpf/rotating-text-effect.jpg) 
  
#### <a name="using-flow-documents"></a>Использование документов нефиксированного формата  
 В дополнение к общим элементам управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предлагает элемент управления макета для представления текста — элемент <xref:System.Windows.Documents.FlowDocument>. Элемент <xref:System.Windows.Documents.FlowDocument> в сочетании с элементом <xref:System.Windows.Controls.DocumentViewer> предоставляет элемент управления для больших объемов текста с различными требованиями к макету. Элементы управления "макет" предоставляют доступ к расширенному оформлению с помощью объекта <xref:System.Windows.Documents.Typography> и свойств, связанных со шрифтами, для других элементов управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 В следующем примере показано текстовое содержимое, размещенное в <xref:System.Windows.Controls.FlowDocumentReader>, которое обеспечивает поддержку поиска, навигации, разбивки на страницы и масштабирования содержимого.  
  
 ![Снимок экрана, показывающий шрифты OpenType.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Дополнительные сведения см. в разделе [Документы в WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Облегченное рисование текста  
 Можно нарисовать текст непосредственно в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объекты с помощью метода <xref:System.Windows.Media.DrawingContext.DrawText%2A> объекта <xref:System.Windows.Media.DrawingContext>. Чтобы использовать этот метод, создайте объект <xref:System.Windows.Media.FormattedText>. Этот объект позволяет рисовать многострочный текст, в котором каждый символ в текст можно форматировать отдельно. Функциональность объекта <xref:System.Windows.Media.FormattedText> содержит большую часть функциональных возможностей флагов DrawText в Windows API. Кроме того, объект <xref:System.Windows.Media.FormattedText> содержит такие функции, как поддержка многоточия, при котором многоточие отображается, когда текст превышает границы. В следующем примере показан текст, имеющий несколько примененных к нему форматов, в том числе линейный градиент на втором и третьем словах.  
  
 ![Отображенный текст с использованием объекта FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg) 
  
 Форматированный текст можно преобразовать в <xref:System.Windows.Media.Geometry>ные объекты, что позволяет создавать другие типы визуально интересного текста. Например, можно создать объект <xref:System.Windows.Media.Geometry>, основанный на контуре текстовой строки.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 В следующих примерах показаны несколько способов создания визуальных эффектов посредством изменения штриха, заливки и выделения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Текст с кистью изображения, примененной к обводке и выделению](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Дополнительные сведения об объекте <xref:System.Windows.Media.FormattedText> см. в разделе [Рисование форматированного текста](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Дополнительное форматирование текста  
 На наиболее расширенном уровне API текста [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предлагает возможность создания пользовательского макета текста с помощью объекта <xref:System.Windows.Media.TextFormatting.TextFormatter> и других типов в пространстве имен <xref:System.Windows.Media.TextFormatting>. <xref:System.Windows.Media.TextFormatting.TextFormatter> и связанные классы позволяют реализовать пользовательский макет текста, который поддерживает собственное определение форматов символов, стилей абзацев, правил переноса строк и других функций макета для международного текста. Существует несколько случаев, когда нужно переопределить реализацию по умолчанию поддержки макета текста [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Однако если был создан элемент управления или приложение редактирования текста, может потребоваться реализация, отличная от реализации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию.  
  
 В отличие от традиционного текстового API, <xref:System.Windows.Media.TextFormatting.TextFormatter> взаимодействует с клиентом макета текста через набор методов обратного вызова. Он требует, чтобы клиент предоставил эти методы в реализации класса <xref:System.Windows.Media.TextFormatting.TextSource>. На следующей схеме показано взаимодействие макета текста между клиентским приложением и <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Схема клиента структуры текста и TextFormatter](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Дополнительные сведения о создании пользовательского макета текста см. в разделе [Дополнительное форматирование текста](advanced-text-formatting.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Общие сведения о технологии ClearType](cleartype-overview.md)
- [Возможности шрифта OpenType](opentype-font-features.md)
- [Рисование форматированного текста](drawing-formatted-text.md)
- [Дополнительное форматирование текста](advanced-text-formatting.md)
- [Text](optimizing-performance-text.md)
- [Типография Майкрософт](https://docs.microsoft.com/typography/)
