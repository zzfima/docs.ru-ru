---
title: Оформление в WPF
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 818d013356c3ca8151e9b5bb675bce4726759f6c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710336"
---
# <a name="typography-in-wpf"></a>Оформление в WPF
В этом разделе содержатся вводные сведения об основных типографических возможностях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Эти возможности включают в себя повышение качества и производительности отрисовки текста, типографическую поддержку [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], расширенный международный текст, улучшенную поддержку шрифтов и новые текстовые API.  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>Улучшенное качество и производительность работы с текстом  
 Текст в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отображается с помощью технологии Microsoft ClearType, что повышает четкость и удобочитаемость текста. Технология ClearType представляет собой программную технологию [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] , разработанную таким образом, улучшая удобочитаемость текста на существующих LCDs (жидкокристаллических дисплеях), таких как экраны ноутбука, карманные экраны и мониторы с плоскими панелями. Технология ClearType использует отрисовку в виде вложенных точек, что позволяет отображать текст с большей точностью до своей реальной фигуры, выполняя символы в дробной части пикселя. Дополнительное разрешение повышает четкость мелких деталей отображаемого текста, значительно облегчая его длительное чтение. Еще одним улучшением технологии [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType в является сглаживание по оси y, которое сглаживает верхние и нижние границы мелких кривых в текстовых символах. Дополнительные сведения о функциях ClearType см. в разделе [Общие сведения о технологии](cleartype-overview.md)ClearType.  
  
 ![Текст со сглаживанием ClearType по оси Y](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Текст со сглаживанием ClearType по оси Y  
  
 Весь конвейер отрисовки текста может поддерживать аппаратное ускорение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], позволяя применять компьютер с минимальными требованиями к оборудованию. Отрисовка, которая не может быть выполнена на аппаратном уровне, использует программный рендеринг. Аппаратное ускорение влияет на все этапы конвейера отрисовки текста — от хранения отдельных глифов, совмещения глифов в выполнении глифов, применения эффектов к применению алгоритма смешения ClearType к окончательно отображаемым выходным данным. Дополнительные сведения об аппаратном ускорении см. в разделе [Уровни графической отрисовки](graphics-rendering-tiers.md).  
  
 ![Диаграмма конвейера отрисовки текста](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Кроме того, анимированный текст, независимо от того, состоит он их знаков или глифов, использует все преимущества возможностей графического оборудования, работающего под управлением [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Это приводит к сглаживанию текстовой анимации.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>Типография с широкими возможностями  
 Формат шрифта [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] является расширением формата [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)]. Формат шрифта [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] был разработан совместно корпорацией [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] и Adobe и предоставляет широкий набор дополнительных типографических возможностей. Объект предоставляет множество дополнительных [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] возможностей шрифтов, таких как стилистические варианты и глифы. <xref:System.Windows.Documents.Typography> [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] предоставляет набор образцов шрифтов [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], разработанных с широкими возможностями, такие как шрифты Pericles и Pescadero. Дополнительные сведения см. в разделе [Пакет образцов шрифтов OpenType](sample-opentype-font-pack.md).  
  
 Шрифт [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Pericles содержит дополнительные глифы, поддерживающие изменение стилей для стандартных наборов глифов. Приведенный ниже текст отображает глифы с изменением стиля.  
  
 ![Текст, использующий стилистические альтернативные глифы OpenType](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Текст, использующий стилистические альтернативные глифы OpenType")  
  
 Swash-глифы являются декоративными глифами, которые используют сложную орнаментацию, часто связанную с каллиграфией. Следующий текст отображает стандартные и swash-глифы для шрифта Pescadero.  
  
 ![Текст, использующий стандартные и swash глифы OpenType](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Текст, использующий стандартные и swash глифы OpenType")  
  
 Дополнительные сведения о возможностях [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] см. в разделе [Возможности шрифта OpenType](opentype-font-features.md).  
  
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
  
- Отдельные <xref:System.Windows.FontWeight>типы <xref:System.Windows.FontStretch>, и<xref:System.Windows.FontStyle>для определения .<xref:System.Windows.Media.FontFamily> Это обеспечивает большую гибкость, чем в программировании [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], в котором логические сочетания курсивного и полужирного шрифта используются для определения семейства шрифтов.  
  
- Направление письма (горизонтальное или вертикальное) обрабатывается в зависимости от имени шрифта.  
  
- Связывание и восстановление шрифта в переносимом файле [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] с использованием технологии составного шрифта. Составные шрифты позволяют конструировать все шрифты многоязычного диапазона. Составные шрифты также предоставляют механизм, который позволяет избежать отображения отсутствующих глифов. Дополнительные сведения см. в разделе Примечания в <xref:System.Windows.Media.FontFamily> классе.  
  
- Международные шрифты, созданные из составных шрифтов с использованием группы одноязыковых шрифтов. Это позволяет избежать затрат ресурсов при разработке шрифтов для нескольких языков.  
  
- Составные шрифты внедряются в документ, тем самым обеспечивая его совместимость. Дополнительные сведения см. в разделе Примечания в <xref:System.Windows.Media.FontFamily> классе.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>Новые API  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет разработчикам несколько текстовых интерфейсов для использования при включении текста в свои приложения. Эти API группируются по трем категориям:  
  
- **Макет и пользовательский интерфейс**. Общие элементы управления текстом для графического пользовательского интерфейса (GUI).  
  
- **Облегченное рисование текста**. Позволяет рисовать текст непосредственно в объектах.  
  
- **Дополнительное форматирование текста**. Позволяет реализовать пользовательский обработчик текста.  
  
### <a name="layout-and-user-interface"></a>Макет и пользовательский интерфейс  
 На самом верхнем уровне функциональности интерфейсы API [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] текста предоставляют общие элементы управления, такие как <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>и. <xref:System.Windows.Controls.TextBox> Эти элементы управления предоставляют основные элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в приложении и способ представления текста и взаимодействия с ним. Такие элементы управления <xref:System.Windows.Controls.RichTextBox> , <xref:System.Windows.Controls.PasswordBox> как и, обеспечивают более расширенную или специализированную обработку текста. И такие классы, <xref:System.Windows.Documents.TextRange>как <xref:System.Windows.Documents.TextSelection>,, <xref:System.Windows.Documents.TextPointer> и обеспечивают полезную обработку текста. Эти [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы управления предоставляют такие свойства <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>как, <xref:System.Windows.Controls.Control.FontStyle%2A>и, которые позволяют управлять шрифтом, используемым для отрисовки текста.  
  
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
  
 <xref:System.Windows.Media.TextEffect> Объект — это вспомогательный объект, который позволяет обрабатывать текст как одну или несколько групп символов в текстовой строке. В следующем примере показан поворот отдельных символов. Поворот каждого символа осуществляется независимо от других с интервалом в 1 секунду.  
  
 ![Снимок экрана текстового эффекта: повернутый текст](./media/typography-in-wpf/rotating-text-effect.jpg) 
  
#### <a name="using-flow-documents"></a>Использование документов нефиксированного формата  
 Помимо стандартных [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов управления, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предлагает элемент управления макетом <xref:System.Windows.Documents.FlowDocument> для представления текста — элемент. Элемент в сочетании <xref:System.Windows.Controls.DocumentViewer> с элементом предоставляет элемент управления для больших объемов текста с различными требованиями к макету. <xref:System.Windows.Documents.FlowDocument> Элементы управления "макет" предоставляют доступ к расширенному оформлению с помощью <xref:System.Windows.Documents.Typography> свойств объекта и шрифта других [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементов управления.  
  
 В следующем примере показано текстовое содержимое, размещенное <xref:System.Windows.Controls.FlowDocumentReader>в, которое обеспечивает поддержку поиска, навигации, разбивки на страницы и масштабирования содержимого.  
  
 ![Снимок экрана, показывающий шрифты OpenType.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Дополнительные сведения см. в разделе [Документы в WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Облегченное рисование текста  
 Текст можно нарисовать непосредственно в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объектах с <xref:System.Windows.Media.DrawingContext.DrawText%2A> помощью метода <xref:System.Windows.Media.DrawingContext> объекта. Чтобы использовать этот метод, создайте <xref:System.Windows.Media.FormattedText> объект. Этот объект позволяет рисовать многострочный текст, в котором каждый символ в текст можно форматировать отдельно. Функциональность <xref:System.Windows.Media.FormattedText> объекта содержит большую часть функциональных возможностей флагов DrawText в Windows API. Кроме того <xref:System.Windows.Media.FormattedText> , объект содержит такие функции, как поддержка многоточия, при котором многоточие отображается, когда текст превышает границы. В следующем примере показан текст, имеющий несколько примененных к нему форматов, в том числе линейный градиент на втором и третьем словах.  
  
 ![Отображенный текст с использованием объекта FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg) 
  
 Форматированный текст можно преобразовать в <xref:System.Windows.Media.Geometry> объекты, что позволяет создавать другие типы визуально интересного текста. Например, можно создать <xref:System.Windows.Media.Geometry> объект на основе контура текстовой строки.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 В следующих примерах показаны несколько способов создания визуальных эффектов посредством изменения штриха, заливки и выделения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Текст с кистью изображения, примененной к обводке и выделению](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Дополнительные сведения <xref:System.Windows.Media.FormattedText> об объекте см. в разделе [Рисование форматированного текста](drawing-formatted-text.md).  
  
### <a name="advanced-text-formatting"></a>Дополнительное форматирование текста  
 На наиболее продвинутых уровнях API [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] текста предусмотрена возможность создания пользовательского макета текста с <xref:System.Windows.Media.TextFormatting.TextFormatter> помощью объекта <xref:System.Windows.Media.TextFormatting> и других типов в пространстве имен. Связанные <xref:System.Windows.Media.TextFormatting.TextFormatter> классы и позволяют реализовать пользовательский макет текста, который поддерживает собственное определение форматов символов, стилей абзацев, правил переноса строк и других функций макета для международного текста. Существует несколько случаев, когда нужно переопределить реализацию по умолчанию поддержки макета текста [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Однако если был создан элемент управления или приложение редактирования текста, может потребоваться реализация, отличная от реализации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию.  
  
 В <xref:System.Windows.Media.TextFormatting.TextFormatter> отличие от традиционного текстового API, взаимодействует с клиентом макета текста через набор методов обратного вызова. Он требует, чтобы клиент предоставил эти методы в реализации <xref:System.Windows.Media.TextFormatting.TextSource> класса. На следующей диаграмме показано взаимодействие макета текста между клиентским приложением и <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Схема клиента структуры текста и TextFormatter](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Дополнительные сведения о создании пользовательского макета текста см. в разделе [Дополнительное форматирование текста](advanced-text-formatting.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Общие сведения о технологии ClearType](cleartype-overview.md)
- [Возможности шрифта OpenType](opentype-font-features.md)
- [Рисование форматированного текста](drawing-formatted-text.md)
- [Дополнительное форматирование текста](advanced-text-formatting.md)
- [Text](optimizing-performance-text.md)
- [Типография Майкрософт](https://docs.microsoft.com/typography/)
