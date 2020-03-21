---
title: Типографская разметка
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 501a4221c99d405484a2fb908641d27d1f38f266
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187353"
---
# <a name="typography-in-wpf"></a>Оформление в WPF
В этом разделе содержатся вводные сведения об основных типографических возможностях [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Эти функции включают в себя улучшение качества и производительности визуализации текста, поддержку типографии OpenType, расширенный международный текст, расширенную поддержку шрифтов и новые интерфейсы программирования текстовых приложений (AA).  
  
<a name="Improved_Quality_and_Performance_of_Text"></a>
## <a name="improved-quality-and-performance-of-text"></a>Улучшенное качество и производительность работы с текстом  
 Текст [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вотугает с помощью Microsoft ClearType, что повышает ясность и читаемость текста. ClearType — это технология программного обеспечения, разработанная корпорацией Майкрософт, которая улучшает читаемость текста на существующих LCD (Liquid Crystal Displays), таких как экраны ноутбуков, карманные экраны ПК и плоские мониторы. ClearType использует субпиксельную визуализацию, которая позволяет отображать текст с большей точностью к его истинной форме путем выравнивания символов на дробной части пикселя. Дополнительное разрешение повышает четкость мелких деталей отображаемого текста, значительно облегчая его длительное чтение. Еще одно улучшение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ClearType в это y-направление анти-алиазирования, которое разглаживает вершины и днища мелких кривых в текстовых символов. Для получения более подробной информации о функциях ClearType [см.](cleartype-overview.md)  
  
 ![Текст со сглаживанием ClearType по оси Y](./media/typography-in-wpf/text-y-direction-antialiasing.gif)  
Текст со сглаживанием ClearType по оси Y  
  
 Весь конвейер отрисовки текста может поддерживать аппаратное ускорение в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], позволяя применять компьютер с минимальными требованиями к оборудованию. Отрисовка, которая не может быть выполнена на аппаратном уровне, использует программный рендеринг. Аппаратно-ускорение влияет на все фазы конвейера визуализации текста – от хранения отдельных глифов, композиций глифов в глиф-бегах, применения эффектов до применения алгоритма смешивания ClearType до окончательного отображаемого вывода. Дополнительные сведения об аппаратном ускорении см. в разделе [Уровни графической отрисовки](graphics-rendering-tiers.md).  
  
 ![Диаграмма конвейера отрисовки текста](./media/typography-in-wpf/text-rendering-pipeline.png)  
  
 Кроме того, анимированный текст, независимо от того, состоит он их знаков или глифов, использует все преимущества возможностей графического оборудования, работающего под управлением [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Это приводит к сглаживанию текстовой анимации.  
  
<a name="Rich_Typography"></a>
## <a name="rich-typography"></a>Типография с широкими возможностями  
 Формат шрифта OpenType является продолжением формата шрифта TrueType®. Формат шрифта OpenType был разработан совместно microsoft и Adobe и предоставляет широкий ассортимент передовых типографских функций. Объект <xref:System.Windows.Documents.Typography> предоставляет многие из расширенных особенностей шрифтов OpenType, таких как стилистические альтернативы и swashes. Windows SDK предоставляет набор образцов шрифтов OpenType, которые разработаны с богатыми функциями, такими как шрифты Pericles и Pescadero. Дополнительные сведения см. в разделе [Пакет образцов шрифтов OpenType](sample-opentype-font-pack.md).  
  
 Шрифт Pericles OpenType содержит дополнительные глифы, которые обеспечивают стилистические альтернативы стандартному набору глифов. Приведенный ниже текст отображает глифы с изменением стиля.  
  
 ![Текст, использующий глифы с изменением стилей OpenType](./media/typography-in-wpf/opentype-stylistic-alternate-glyphs.gif "Текст, использующий глифы с изменением стилей OpenType")  
  
 Swash-глифы являются декоративными глифами, которые используют сложную орнаментацию, часто связанную с каллиграфией. Следующий текст отображает стандартные и swash-глифы для шрифта Pescadero.  
  
 ![Текст, использующий стандартные и swash глифы OpenType](./media/typography-in-wpf/opentype-standard-swash-glyphs.gif "Текст, использующий стандартные и swash глифы OpenType")  
  
 Для получения более подробной информации о функциях OpenType [см.](opentype-font-features.md)  
  
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
  
- Отдельные, <xref:System.Windows.FontWeight> <xref:System.Windows.FontStretch> <xref:System.Windows.FontStyle> и типы <xref:System.Windows.Media.FontFamily>для определения . Это обеспечивает большую гибкость, чем в программировании Win32, в котором Boolean комбинации курсивом и смелым используются для определения семейства шрифтов.  
  
- Направление письма (горизонтальное или вертикальное) обрабатывается в зависимости от имени шрифта.  
  
- Ссылка шрифтов и обратное шрифта в портативном файле XML, используя технологию композитного шрифта. Составные шрифты позволяют конструировать все шрифты многоязычного диапазона. Составные шрифты также предоставляют механизм, который позволяет избежать отображения отсутствующих глифов. Для получения дополнительной информации, <xref:System.Windows.Media.FontFamily> смотрите замечания в классе.  
  
- Международные шрифты, созданные из составных шрифтов с использованием группы одноязыковых шрифтов. Это позволяет избежать затрат ресурсов при разработке шрифтов для нескольких языков.  
  
- Составные шрифты внедряются в документ, тем самым обеспечивая его совместимость. Для получения дополнительной информации, <xref:System.Windows.Media.FontFamily> смотрите замечания в классе.  
  
<a name="New_Text_APIs"></a>
## <a name="new-text-application-programming-interfaces-apis"></a>Новые API  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет разработчикам несколько текстовых ABI для использования при включении текста в свои приложения. Эти AA сгруппированы по трем категориям:  
  
- **Layout и пользовательский интерфейс**. Общие текстовые элементы управления графическим пользовательским интерфейсом (GUI).  
  
- **Легкий рисунок текста**. Позволяет рисовать текст непосредственно в объектах.  
  
- **Расширенный форматирование текста**. Позволяет реализовать пользовательский обработчик текста.  
  
### <a name="layout-and-user-interface"></a>Макет и пользовательский интерфейс  
 На самом высоком уровне функциональности, текстовые [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] AIS <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.TextBlock>обеспечивают <xref:System.Windows.Controls.TextBox>общие элементы управления, такие как , и . Эти элементы управления предоставляют основные элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в приложении и способ представления текста и взаимодействия с ним. Элементы <xref:System.Windows.Controls.RichTextBox> управления, такие как и <xref:System.Windows.Controls.PasswordBox> включить более продвинутые или специализированные текстовые обработки. И классы, <xref:System.Windows.Documents.TextSelection>такие <xref:System.Windows.Documents.TextPointer> как <xref:System.Windows.Documents.TextRange>, и позволяют полезные манипуляции текстом. Эти [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы управления <xref:System.Windows.Controls.Control.FontFamily%2A> <xref:System.Windows.Controls.Control.FontSize%2A>предоставляют <xref:System.Windows.Controls.Control.FontStyle%2A>такие свойства, как, и , которые позволяют управлять шрифтом, который используется для визуализации текста.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>Использование эффектов точечных рисунков и текстовых эффектов  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет создавать визуально интересные применения текста, используя такие возможности, как эффекты точечных рисунков, преобразования и текстовые эффекты. В следующем примере показан типичный эффект тени, примененный к тексту.  
  
 ![Текстовая тень с мягкостью &#61; 0,25](./media/typography-in-wpf/drop-shadow-text-effect.jpg)
  
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
  
 Объект <xref:System.Windows.Media.TextEffect> является объектом-помощником, который позволяет рассматривать текст как одну или несколько групп символов в текстовой строке. В следующем примере показан поворот отдельных символов. Поворот каждого символа осуществляется независимо от других с интервалом в 1 секунду.  
  
 ![Снимок экрана текстового эффекта: повернутый текст](./media/typography-in-wpf/rotating-text-effect.jpg)
  
#### <a name="using-flow-documents"></a>Использование документов нефиксированного формата  
 В дополнение к [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] общим [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементам управления, предлагает управление <xref:System.Windows.Documents.FlowDocument> компоновкой для текстового представления-элемента. Элемент, <xref:System.Windows.Documents.FlowDocument> в сочетании <xref:System.Windows.Controls.DocumentViewer> с элементом, обеспечивает контроль за большим количеством текста с различными требованиями макета. Элементы управления макетами обеспечивают доступ <xref:System.Windows.Documents.Typography> к расширенной типографии [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] через объект и связанные с шрифтом свойства других элементов управления.  
  
 В следующем примере показан <xref:System.Windows.Controls.FlowDocumentReader>текстовый контент, размещенный в поддержке поиска, навигации, pagination и масштабирования содержимого.  
  
 ![Скриншот, на который отображается шрифты OpenType.](./media/typography-in-wpf/typography-text-flowdocumentreader.png)
  
 Дополнительные сведения см. в разделе [Документы в WPF](documents-in-wpf.md).  
  
### <a name="lightweight-text-drawing"></a>Облегченное рисование текста  
 Вы можете нарисовать текст непосредственно к [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объектам с помощью <xref:System.Windows.Media.DrawingContext.DrawText%2A> метода <xref:System.Windows.Media.DrawingContext> объекта. Чтобы использовать этот метод, <xref:System.Windows.Media.FormattedText> вы создаете объект. Этот объект позволяет рисовать многострочный текст, в котором каждый символ в текст можно форматировать отдельно. Функциональность <xref:System.Windows.Media.FormattedText> объекта содержит большую часть функциональности флагов DrawText в API Windows. Кроме того, <xref:System.Windows.Media.FormattedText> объект содержит такие функции, как поддержка эллипсиса, в которой эллипсис отображается, когда текст выходит за пределы своих границ. В следующем примере показан текст, имеющий несколько примененных к нему форматов, в том числе линейный градиент на втором и третьем словах.  
  
 ![Отображенный текст с использованием объекта FormattedText](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)
  
 Вы можете конвертировать <xref:System.Windows.Media.Geometry> отформатированный текст в объекты, что позволяет создавать другие типы визуально интересного текста. Например, можно создать <xref:System.Windows.Media.Geometry> объект на основе контура строки текста.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](./media/typography-in-wpf/text-outline-linear-gradient.jpg)  
  
 В следующих примерах показаны несколько способов создания визуальных эффектов посредством изменения штриха, заливки и выделения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![Текст с кистью изображения, примененной к штриху](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![Текст с изображением кисти, нанесенной на штрих и выделение](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 Для получения дополнительной <xref:System.Windows.Media.FormattedText> информации об объекте [см.](drawing-formatted-text.md)  
  
### <a name="advanced-text-formatting"></a>Дополнительное форматирование текста  
 На самом продвинутом уровне [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aIS текста, предлагает вам возможность создавать <xref:System.Windows.Media.TextFormatting.TextFormatter> пользовательский макет <xref:System.Windows.Media.TextFormatting> текста с помощью объекта и других типов в пространстве имен. Связанные <xref:System.Windows.Media.TextFormatting.TextFormatter> и связанные классы позволяют реализовать пользовательский макет текста, который поддерживает ваше собственное определение форматов символов, стилей абзацев, правил нарушения строк и других функций макета для международного текста. Существует несколько случаев, когда нужно переопределить реализацию по умолчанию поддержки макета текста [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Однако если был создан элемент управления или приложение редактирования текста, может потребоваться реализация, отличная от реализации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию.  
  
 В отличие от традиционного <xref:System.Windows.Media.TextFormatting.TextFormatter> API текста, он взаимодействует с клиентом макета текста через набор методов обратного вызова. Это требует от клиента предоставить эти методы в реализации <xref:System.Windows.Media.TextFormatting.TextSource> класса. Следующая диаграмма иллюстрирует взаимодействие макета текста между <xref:System.Windows.Media.TextFormatting.TextFormatter>клиентским приложением и .  
  
 ![Схема клиента структуры текста и TextFormatter](./media/typography-in-wpf/text-layout-text-formatter-interaction.png)  
  
 Дополнительные сведения о создании пользовательского макета текста см. в разделе [Дополнительное форматирование текста](advanced-text-formatting.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.FormattedText>
- <xref:System.Windows.Media.TextFormatting.TextFormatter>
- [Общие сведения о технологии ClearType](cleartype-overview.md)
- [Возможности шрифта OpenType](opentype-font-features.md)
- [Рисование форматированного текста](drawing-formatted-text.md)
- [Дополнительное форматирование текста](advanced-text-formatting.md)
- [Текст](optimizing-performance-text.md)
- [Типография Майкрософт](https://docs.microsoft.com/typography/)
