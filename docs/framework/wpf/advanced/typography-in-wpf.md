---
title: "Оформление в WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "оформление, об оформлении"
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Оформление в WPF
В этом разделе содержится введение в основные типографические возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Эти возможности включают повышение качества и производительности отрисовки текста, типографическую поддержку [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)], расширенный международный текст, улучшенную поддержку шрифтов и новые текстовые API.  
  
   
  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## Улучшенное качество и производительность работы с текстом  
 Текст в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] отрисовывается с помощью [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)], что улучшает четкость и читаемость текста.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] — это программная технология, разработанная [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] для улучшения удобочитаемости текста на современных ЖК\-мониторах \(жидкокристаллических дисплеях\), например экранах ноутбуков, карманных ПК и плоскопанельных мониторах.  [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] применяет отрисовку на субпиксельном уровне, которая позволяет отображать текст с повышенной точностью формы, выравнивая символы до дробной части пикселя.  Дополнительное разрешение повышает четкость мелких деталей отображаемого текста, значительно облегчая его длительное чтение.  Другим улучшением [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является применение устранение контурных неровностей по направлению оси y, которое сглаживает неровные края на верхних и нижних частях в текстовых знаках.  Дополнительные сведения о возможностях [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] см. в разделе [Общие сведения о технологии ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md).  
  
 ![Текст со сглаживанием ClearType по оси Y](../../../../docs/framework/wpf/advanced/media/typographyinwpf02.png "TypographyInWPF02")  
Текст со сглаживанием ClearType по оси Y  
  
 Весь конвейер отрисовки текста может поддерживать аппаратное ускорение в приложении [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], позволяя применять компьютер с минимальными требованиями к оборудованию.  Отрисовка, которая не может быть выполнено на аппаратном уровне, использует программный рендеринг.  Аппаратное ускорение влияет на все этапы конвейерной подготовки текста — от сохранения отдельных глифов, их компоновки в глифы для выполнения, применения эффектов и до применения алгоритма смешивания [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] для окончательной отрисовки.  Дополнительные сведения об аппаратном ускорении содержатся в разделе [Уровни графической отрисовки](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md).  
  
 ![Диаграмма конвейера отрисовки текста](../../../../docs/framework/wpf/advanced/media/typographyinwpf01.png "TypographyInWPF01")  
Диаграмма конвейера отрисовки текста  
  
 Кроме того, анимированный текст, независимо от того, состоит он их знаков или глифов, использует все преимущества возможностей графического оборудования, работающего под управлением [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Это приводит к сглаживанию текстовой анимации.  
  
<a name="Rich_Typography"></a>   
## Типография с широкими возможностями  
 Формат шрифта [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] является расширением формата [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)].  Формат шрифта [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] был разработан совместно корпорацией [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] и Adobe и предоставляет широкий набор дополнительных типографических возможностей.  Объект <xref:System.Windows.Documents.Typography> поддерживает множество дополнительных возможностей шрифтов [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], таких как изменение стилей и swash.  [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] предоставляет набор образцов шрифтов [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)], которые разработаны с широкими возможности, например, шрифты Pericles и Pescadero.  Дополнительные сведения см. в разделе [Образец пакета шрифтов OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 Шрифт [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] Pericles содержит дополнительные глифы, поддерживающие изменение стилей для стандартных наборов глифов.  Следующий текст отображает глифы с изменением стиля.  
  
 ![Текст, использующий глифы с изменением стилей OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont02.png "opentypefont02")  
Текст, в котором используются стилистически альтернативные глифы OpenType  
  
 Swash глифы являются декоративными глифами, которые используют сложную орнаментацию, часто связанную с каллиграфией.  Следующий текст отображает стандартные и swash глифы для шрифта Pescadero.  
  
 ![Текст, использующий стандартные и swash глифы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont08.png "opentypefont08")  
Текст, в котором используются стандартные и орнаментированные глифы OpenType  
  
 Дополнительные сведения о возможностях [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] см. в разделе [Возможности шрифта OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md).  
  
<a name="Enhanced_International_Text_Support"></a>   
## Расширенная многоязыковая поддержка текста  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает расширение международного текста, предоставляя следующие возможности:  
  
-   Автоматическая расстановка пробелов во всех системах письма с использованием адаптивного измерения.  
  
-   Широкая поддержка международного текста.  Дополнительные сведения см. в разделе [Глобализация для WPF](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md).  
  
-   Управляемый языком разрыв строки, расстановка переносов и выравнивание.  
  
<a name="Enhanced_Font_Support"></a>   
## Расширенная поддержка шрифтов  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет расширенную поддержку шрифта с помощью следующих возможностей:  
  
-   Юникод для всех текстов.  Поведение шрифта и выбор, больше не требующий набора символов или кодовой страницы.  
  
-   Поведение шрифта зависит от глобальных настроек, таких как язык системы.  
  
-   Разделение типов <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch> и <xref:System.Windows.FontStyle> для определения <xref:System.Windows.Media.FontFamily>.  Это обеспечивает большую гибкость, чем в программировании [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)], в котором логические сочетания курсивного и полужирного шрифта используются для определения семейства шрифтов.  
  
-   Направление письма \(горизонтальное или вертикальное\) обрабатывается в зависимости от имени шрифта.  
  
-   Связывание и восстановление шрифта в переносимом файле [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] с использованием технологии составного шрифта.  Составные шрифты позволяют конструировать все шрифты многоязычного диапазона.  Составные шрифты также предоставляют механизм, который позволяет избежать отображения отсутствующих глифов.  Дополнительные сведения см. в примечаниях в классе <xref:System.Windows.Media.FontFamily>.  
  
-   Международные шрифты, созданные из составных шрифтов с использованием группы одноязыковых шрифтов.  Это позволяет избежать затрат ресурсов при разработке шрифтов для нескольких языков.  
  
-   Составные шрифты внедряются в документ, тем самым обеспечивая его совместимость.  Дополнительные сведения см. в примечаниях в классе <xref:System.Windows.Media.FontFamily>.  
  
<a name="New_Text_APIs"></a>   
## Новые API  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет для разработчиков несколько текстовых [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], которые используются при включении текста в приложения.  Эти [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] сгруппированы в три категории:  
  
-   **Макет и пользовательский интерфейс**.  Общие элементы управления текстом для [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)].  
  
-   **Облегченное рисование текста**.  Предоставляет возможность рисования текста непосредственно в объекты.  
  
-   **Дополнительное форматирование текста**.  Позволяет реализовать пользовательский обработчик текста.  
  
### Макет и пользовательский интерфейс  
 На высшем уровне функциональности текстовый [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] предоставляет общие элементы управления [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], такие как <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock> и <xref:System.Windows.Controls.TextBox>.  Эти элементы управления обеспечивают основные элементы [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в приложении и легкий способ представления текста и взаимодействия с ним.  Элемент управления, такие как <xref:System.Windows.Controls.RichTextBox> и <xref:System.Windows.Controls.PasswordBox>, обеспечивают более расширенную или специальную обработку текста.  И классы, такие как <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection> и <xref:System.Windows.Documents.TextPointer>, предоставляют удобное управление текстом.  Эти элементы управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] предоставляют свойства, такие как <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A> и <xref:System.Windows.Controls.Control.FontStyle%2A>, позволяющие управлять шрифтами, которые используются для отображения текста.  
  
#### Использование эффектов точечных рисунков и текстовых эффектов  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] позволяет создавать визуально интересные применения текста, используя такие возможности, как эффекты точечных рисунков, преобразования и текстовые эффекты.  Следующий пример показывает типичный эффект тени, примененный к тексту.  
  
 ![Тень текста с мягкостью &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.png "ShadowText01")  
Текст с тенью  
  
 Следующий пример показывает эффект тени и шума, примененный к тексту.  
  
 ![Тень текста с шумом](../../../../docs/framework/wpf/advanced/media/shadowtext04.png "ShadowText04")  
Текст с тенью и шумом  
  
 В следующем примере показан эффект внешнего свечения, примененный к тексту.  
  
 ![Тень текста с использованием OuterGlowBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext05.png "ShadowText05")  
Текст с эффектом свечения  
  
 В следующем примере показан эффект размытия, примененный к тексту.  
  
 ![Тень текста с использованием BlurBitmapEffect](../../../../docs/framework/wpf/advanced/media/shadowtext06.png "ShadowText06")  
Текст с эффектом размытия  
  
 Следующий пример показывает вторую строку текста, масштабированную на 150% вдоль оси x, и третью строку текста, масштабированную на 150% вдоль оси y.  
  
 ![Текст, масштабируемый с использованием ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.png "TransformedText02")  
Текст с использованием ScaleTransform  
  
 В следующем примере показан текст, наклоненный вдоль оси x.  
  
 ![Текст, искаженный с использованием SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.png "TransformedText03")  
Текст с использованием SkewTransform  
  
 Объект <xref:System.Windows.Media.TextEffect> является вспомогательным объектом, который позволяет обрабатывать текст как одну или несколько групп символов в текстовой строке.  В следующем примере демонстрируется поворот отдельных символов.  Поворот каждого символа осуществляется независимо от других с интервалом в 1 секунду.  
  
 ![Снимок экрана текстового эффекта: повернутый текст](../../../../docs/framework/wpf/advanced/media/texteffect01.png "TextEffect01")  
Пример анимации текстового эффекта "Вращение"  
  
#### Использование документов нефиксированного формата  
 Дополнительно к общим элементам управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предлагает элемент управления макетом для презентации текста — элемент <xref:System.Windows.Documents.FlowDocument>.  Элемент <xref:System.Windows.Documents.FlowDocument> в сочетании с элементом <xref:System.Windows.Controls.DocumentViewer> предоставляет элемент управления для больших объемов текста с различными требованиями к макету.  Элементы управления макета обеспечивают доступ к дополнительным возможностям оформления посредством объекта <xref:System.Windows.Documents.Typography> и свойств, связанных со шрифтами других элементов управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 Следующий пример показывает текстовое содержимое, размещенное в объекте <xref:System.Windows.Controls.FlowDocumentReader>, который обеспечивает поддержку поиска, переходов, разбиения на страницы и масштабирования содержимого.  
  
 ![Снимок экрана примера использования шрифтов OpenType](../../../../docs/framework/wpf/advanced/media/typographyinwpf-03.png "TypographyInWPF\_03")  
Текст, размещенный в объекте FlowDocumentReader  
  
 Дополнительные сведения см. в разделе [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
### Облегченное рисование текста  
 Можно рисовать текст непосредственно в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] объекты с помощью метода <xref:System.Windows.Media.DrawingContext.DrawText%2A> объекта <xref:System.Windows.Media.DrawingContext>.  Чтобы использовать этот метод, создайте объект <xref:System.Windows.Media.FormattedText>.  Этот объект позволяет рисовать многострочный текст, в котором каждый символ можно форматировать отдельно.  Функциональные возможности объекта <xref:System.Windows.Media.FormattedText> содержат большую часть функциональных возможностей флагов DrawText в API Win32.  Кроме того, объект <xref:System.Windows.Media.FormattedText> содержит функциональные возможности, такие как поддержку многоточия, при котором многоточие отображается, когда текст выходит за границы.  В следующем примере показан текст, имеющий несколько примененных к нему форматов, в том числе — линейный градиент на втором и третьем слове.  
  
 ![Отображенный текст с использованием объекта FormattedText](../../../../docs/framework/wpf/advanced/media/formattedtext01.png "FormattedText01")  
Отображенный текст с использованием объекта FormattedText  
  
 Можно преобразовать форматированный текст в объекты <xref:System.Windows.Media.Geometry>, что позволит создавать другие типы наглядного текста.  Например, можно создать объект <xref:System.Windows.Media.Geometry>, основанный на контуре строки текста.  
  
 ![Оконтуривание текста с использованием кисти линейного градиента](../../../../docs/framework/wpf/advanced/media/outlinedtext02.png "OutlinedText02")  
Оконтуривание текста с использованием кисти линейного градиента  
  
 В следующих примерах показаны несколько способов создания визуальных эффектов посредством изменения штриха, заливки и выделения преобразованного текста.  
  
 ![Текст с различными цветами для заполнения штриха](../../../../docs/framework/wpf/advanced/media/outlinedtext03.png "OutlinedText03")  
Пример установки разного цвета для штриха и заливки  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext04.png "OutlinedText04")  
Пример применения кисти к штриху  
  
 ![Текст с кистью изображения, примененной к штриху](../../../../docs/framework/wpf/advanced/media/outlinedtext05.png "OutlinedText05")  
Пример применения кисти к штриху и выделению  
  
 Дополнительные сведения об объекте <xref:System.Windows.Media.FormattedText> см. в разделе [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md).  
  
### Дополнительное форматирование текста  
 На наиболее развитом уровне текстовых [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] приложение [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет возможность создания пользовательской разметки текста с помощью объекта <xref:System.Windows.Media.TextFormatting.TextFormatter> и других типов в пространстве имен <xref:System.Windows.Media.TextFormatting>.  Объект <xref:System.Windows.Media.TextFormatting.TextFormatter> и связанные классы позволяют реализовать макет настраиваемую разметку текста, которая поддерживает пользовательское определение формата символов, стили абзаца, правила разрыва строки и другие возможности разметки для международного текста.  Имеется несколько случаев, когда нужно переопределить реализацию по умолчанию поддержки разметки текста [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Однако если был создан элемент управления или приложение редактирования текста, может потребоваться реализация, отличная от реализации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по умолчанию.  
  
 В отличие от традиционного текстового [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], объект <xref:System.Windows.Media.TextFormatting.TextFormatter> взаимодействует с клиентом разметки текста через набор методов обратного вызова.  Для предоставления этих методов в реализации класса <xref:System.Windows.Media.TextFormatting.TextSource> требуется клиент.  Следующая диаграмма иллюстрирует взаимодействие разметки текста между клиентским приложением и объектом <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Схема клиента структуры текста и TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Взаимодействие между приложением и объектом TextFormatter  
  
 Более подробные сведения о создании макета пользовательской разметки текста содержатся в разделе [Дополнительное форматирование текста](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md).  
  
## См. также  
 <xref:System.Windows.Media.FormattedText>   
 <xref:System.Windows.Media.TextFormatting.TextFormatter>   
 [Общие сведения о технологии ClearType](../../../../docs/framework/wpf/advanced/cleartype-overview.md)   
 [Возможности шрифта OpenType](../../../../docs/framework/wpf/advanced/opentype-font-features.md)   
 [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)   
 [Дополнительное форматирование текста](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Microsoft Typography](http://www.microsoft.com/typography/default.mspx)