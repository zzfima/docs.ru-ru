---
title: "Возможности шрифта OpenType | Microsoft Docs"
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
  - "шрифты OpenType"
  - "Оформление и технологии шрифтов OpenType"
  - "OpenType - технология шрифтов"
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 37
---
# Возможности шрифта OpenType
В этом разделе содержится обзор некоторых основных возможностей [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] технологии шрифтов в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
   
  
<a name="overview"></a>   
## <a name="opentype-font-format"></a>Формат шрифтов OpenType  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Шрифт является расширением [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] формат шрифтов, добавляя поддержку для данных шрифтов PostScript. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Шрифт был разработан совместно корпорацией [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] и Adobe. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]шрифты и операционная система которых поддержку службы [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] шрифты предоставляют пользователям простой способ установки и использования шрифтов, шрифтов содержат ли [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] контуров или контуры CFF (PostScript).  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Шрифт решает следующие задачи разработки:  
  
-   Расширенная многоплатформенная поддержка.  
  
-   Улучшенная поддержка международных кодировок.  
  
-   Улучшенная защита данных шрифта.  
  
-   Меньшие размеры файлов, что делает распространение шрифта более эффективным.  
  
-   Широкий поддержка дополнительного типографского контроля.  
  
> [!NOTE]
>  Windows SDK содержит набор образцов [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] шрифтов, которые можно использовать с [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] приложений. Эти шрифты обеспечивают большинство функций, приведенных в остальной части этого раздела. Дополнительные сведения см. в разделе [примере пакета шрифтов OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md).  
  
 В разделе [спецификации OpenType](http://go.microsoft.com/fwlink/?LinkId=96731) подробные сведения о [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] формат шрифта.  
  
### <a name="advanced-typographic-extensions"></a>Дополнительные типографские расширения  
 Дополнительные типографские таблицы ([!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] макет таблицы) расширяют функциональные возможности шрифтов с эскизами [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] или CFF. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]Макет шрифты содержат дополнительную информацию, которая расширяет возможности шрифтов для поддержки международных оформления высокого качества. Большинство [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] шрифты предоставлять только подмножество общее [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] возможности. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]шрифты обеспечивают следующие возможности.  
  
-   Расширенное сопоставление между символами и знаками, которые поддерживают лигатуры, позиционные формы, альтернатив и другие подстановки шрифтов.  
  
-   Поддержка двумерного позиционирования и вложения глифа.  
  
-   Явные сценариев и язык сведения, содержащиеся в шрифта, поэтому приложение обработки текста соответствующим образом настроить его поведение.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] Макет таблицы описаны более подробно в [«Таблицы файл шрифта»](http://www.microsoft.com/typography/otspec/otff.htm) раздел [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] спецификации.  
  
 Далее в этом обзоре описаны различные гибко визуально интересного [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] функции, предоставляемые свойства <xref:System.Windows.Documents.Typography> объекта. Дополнительные сведения об этом объекте в разделе [оформления класса](#typography_class).  
  
<a name="variants"></a>   
## <a name="variants"></a>Варианты  
 Варианты используются для отображения различных типографских стилей, например верхние и нижние индексы.  
  
### <a name="superscripts-and-subscripts"></a>надстрочные и подстрочные  
 <xref:System.Windows.Documents.Typography.Variants%2A> позволяет установить значения верхнего и нижнего индекса для [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] шрифта.  
  
 Приведенный ниже текст отображает надстрочные знаки для шрифта Palatino Linotype.  
  
 ![Текст, использующий верхние индексы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont14.png "opentypefont14")  
Текст, использующий верхние индексы OpenType  
  
 В следующем примере разметки показано определение верхних для шрифта Palatino Linotype с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 Приведенный ниже текст отображает индексов для шрифта Palatino Linotype.  
  
 ![Текст, использующий нижние индексы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont15.png "opentypefont15")  
Текст, использующий нижние индексы OpenType  
  
 В следующем примере разметки показано определение нижних индексов для шрифта Palatino Linotype с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>Декоративные применения верхних и нижних индексов  
 Также можно использовать верхние и нижние индексы для создания декоративного эффекта текста в смешанном регистре. Приведенный ниже текст отображает текст верхнего и нижнего индекса для шрифта Palatino Linotype. Обратите внимание, что заглавные буквы не затронуты.  
  
 ![Текст, использующий верхние индексы OpenType и индексы](../../../../docs/framework/wpf/advanced/media/opentypefont16.png "opentypefont16")  
Текст, использующий верхние и нижние индексы OpenType  
  
 В следующем примере разметки показано определение верхних и нижних индексов для шрифта с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a>Прописные буквы  
 Прописные буквы — это набор типографических форм, которые отображают текст в прописные глифы. Обычно, когда текст воспроизводится как все прописные, расстояние между буквами может казаться слишком маленьким, а плотность и пропорции символов слишком большими. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]поддерживает множество форматов стилей для прописных букв, включая прописные буквы, малые прописные буквы, титульные буквы и прописные интервалы. Эти форматы стиля позволяют управлять внешним видом прописных букв.  
  
 Приведенный ниже текст отображает стандартные прописных букв для шрифта Pescadero следуют буквы, в стиле «Малые прописные» и «AllSmallCaps». В этом случае для всех трех слов используется тот же размер шрифта.  
  
 ![Текст, использующий прописные буквы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont11.png "opentypefont11")  
Текст, использующий прописные буквы OpenType  
  
 В следующем примере разметки показано определение прописных букв для шрифта Pescadero с помощью свойств <xref:System.Windows.Documents.Typography> объекта. При использовании формата «Малые прописные» начальные прописные буквы учитывается.  
  
 [!code-xml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>Титульные прописные буквы  
 Титульные прописные буквы имеют меньшую плотность и пропорции и разработаны для придания более элегантный вида, чем обычные прописные буквы. Титульные прописные буквы обычно используются в больших размерах шрифта в заголовках. Приведенный ниже текст отображает обычные и титульные прописные буквы для шрифта Pescadero. Обратите внимание, узкую текста во второй строке.  
  
 ![Текст, использующий титульные прописные буквы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont20.png "OpenTypeFont20")  
Текст, использующий титульные прописные буквы OpenType  
  
 В следующем примере разметки показано определение титульных прописных букв для шрифта Pescadero с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>Прописные интервалы  
 Прописной интервал является функция, которая позволяет предоставить дополнительные интервалы, при использовании только прописные буквы в тексте. Прописные буквы обычно предназначены для наложения со строчной буквы. Интервал, который кажется привлекательным между заглавной буквы и строчные буквы, может выглядеть слишком маленьким при использовании прописными буквами. Приведенный ниже текст отображает обычный и прописной интервал для шрифта Pescadero.  
  
 ![Текст, использующий прописной интервал OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont21.png "OpenTypeFont21")  
Текст, использующий прописной интервал OpenType  
  
 В следующем примере разметки показано определение прописной интервал для шрифта Pescadero с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a>Лигатуры  
 Лигатуры — это два или более глифов, формирующихся в один глиф для создания более читаемого или привлекательного текста. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]шрифты поддерживают четыре типа лигатур:  
  
-   **Стандартные лигатуры**. Разработаны для улучшения удобочитаемости. Стандартные лигатуры включают «fi», «fl» и «ff».  
  
-   **Контекстные лигатуры**. Разработаны для улучшения удобочитаемости, предоставляя более эффективного поведения соединения символов, составляющих лигатуры.  
  
-   **Избирательные лигатуры**. Предназначены для украшения и не применяются специально для удобочитаемости.  
  
-   **Исторические лигатуры**. Должен быть исторические и не предназначены специально для удобочитаемости.  
  
 Следующий текст отображает стандартные глифы лигатуры для шрифта Pericles.  
  
 ![Текст, использующий стандартные лигатуры OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont04.png "opentypefont04")  
Текст, использующий стандартные лигатуры OpenType  
  
 В следующем примере разметки показано определение стандартных глифов лигатуры для шрифта Pericles с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 Следующий текст отображает избирательные глифы лигатуры для шрифта Pericles.  
  
 ![Текст, использующий избирательные лигатуры OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont05.png "opentypefont05")  
Текст, использующий избирательные лигатуры OpenType  
  
 В следующем примере разметки показано определение избирательных глифов лигатуры для шрифта Pericles с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 По умолчанию [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] шрифтов в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] используют стандартные лигатуры. Например при использовании шрифта Palatino Linotype стандартные лигатуры «fi», «ff» и «fl» отображаются как глиф объединенных символов. Обратите внимание, что пары знаков для каждой стандартной лигатуры касаются друг друга.  
  
 ![Текст, использующий стандартные лигатуры OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont06.png "opentypefont06")  
Текст, использующий стандартные лигатуры OpenType  
  
 Однако функции стандартных лигатур можно отключить, чтобы стандартные лигатуры, такие как «ff» отображается как два отдельных глифа, а не как глиф объединенных символов.  
  
 ![Текст, использующий неактивные стандартные лигатуры OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont07.png "opentypefont07")  
Текст, использующий неактивные стандартные лигатуры OpenType  
  
 В следующем примере разметки показано, как отключить стандартные глифы лигатур для шрифта Palatino Linotype с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a>Swash-глифы  
 Swash-глифы являются декоративными глифами, которые используют сложную орнаментацию, часто связанную с каллиграфией. Следующий текст отображает стандартные и swash глифы для шрифта Pescadero.  
  
 ![Текст, использующий стандартные и swash глифы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont08.png "opentypefont08")  
Текст, использующий стандартные и swash глифы OpenType  
  
 Swash-глифы часто используются как декоративные элементы в коротких фразах, таких как объявления о событиях. Следующий текст использует swash-глифы для выделения прописных букв имени события.  
  
 ![Текст, использующий swash глифы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont09.png "opentypefont09")  
Текст, использующий swash глифы OpenType  
  
 В следующем примере разметки показано определение swash-глифы для шрифта с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>Контекстные swash-глифы  
 Определенные комбинации swash-глифов можно непривлекательно, например перекрывать подстрочные элементы на соседних буквах. Использование контекстных swash-глифов позволяет использовать замещающий swash-глиф, создающий улучшения внешнего вида. Следующий текст показывает то же слово до и после применения контекстных swash-глифов.  
  
 ![Текст, использующий контекстные swash-глифы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont19.png "OpenTypeFont19")  
Текст, использующий контекстные swash-глифы OpenType  
  
 В следующем примере разметки показано определение контекстных swash-глифов для шрифта Pescadero с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a>Варианты  
 Варианты — это глифы, которые могут быть заменены на стандартный глиф. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]шрифты, например Pericles, используемый в следующих примерах, могут содержать альтернативные глифы, которые можно использовать для создания различного внешнего вида для текста. Следующий текст отображает стандартные глифы для шрифта Pericles.  
  
 ![Текст, использующий стандартные глифы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont01.png "opentypefont01")  
Текст, использующий стандартные глифы OpenType  
  
 Pericles [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] содержит дополнительные глифы, поддерживающие изменение стилей для стандартных наборов глифов. Приведенный ниже текст отображает глифы с изменением стиля.  
  
 ![Текст, использующий стилистически альтернативные глифы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont02.png "opentypefont02")  
Текст, использующий глифы с изменением стилей OpenType  
  
 В следующем примере разметки показано определение стилистических глифов для шрифта Pericles с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 Следующий текст отображает несколько дополнительных глифов стилистических вариантов для шрифта Pericles.  
  
 ![Текст, использующий стилистически альтернативные глифы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont03.png "opentypefont03")  
Текст, использующий глифы с изменением стилей OpenType  
  
 В следующем примере разметки показано определение этих дополнительных глифов стилистических вариантов.  
  
 [!code-xml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>Случайные контекстные варианты  
 Случайные контекстные альтернативы предоставляют несколько заменяющих глифов для одного символа. При реализации со шрифтами, эта функция может имитировать рукописного ввода с помощью набора случайно выбранных глифов с незначительными различиями в внешний вид. Следующий текст использует случайные контекстные глифы alternate для шрифта Lindsey. Обратите внимание, что буква «» немного отличается  
  
 ![Текст, использующий случайные контекстные модификаторы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont23.png "OpenTypeFont23")  
Текст, использующий случайные контекстные alternate-глифы OpenType  
  
 В следующем примере разметки показано определение случайных контекстных вариантов для шрифта Lindsey с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>Исторические формы  
 Исторические формы являются типографские соглашения, принятые в прошлом. Приведенный ниже текст отображает фразу «Бостон, штат Массачусетс» с помощью исторические формы глифов для шрифта Palatino Linotype.  
  
 ![Текст, использующий исторические формы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont10.png "opentypefont10")  
Текст, использующий исторические формы OpenType  
  
 В следующем примере разметки показано определение исторических форм для шрифта Palatino Linotype с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a>Числовые стили  
 Шрифты OpenType поддерживают большое количество функций, которые могут использоваться с числовыми значениями в тексте.  
  
### <a name="fractions"></a>Доли секунды  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]шрифты поддерживают стили для дробей, включая диагональные и вертикальные дроби.  
  
 Приведенный ниже текст отображает стилей дробей для шрифта Palatino Linotype.  
  
 ![Текст, использующий OpenType диагональные и вертикальные дроби](../../../../docs/framework/wpf/advanced/media/opentypefont12.png "opentypefont12")  
Текст, использующий диагональные и вертикальные дроби OpenType  
  
 В следующем примере разметки показано определение стилей дробей для шрифта Palatino Linotype с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>Старый стиль числа  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]шрифты поддерживают формат старого стиля чисел. Этот формат полезен для отображения цифр в стилях, которые уже не являются стандартными. Следующий текст отображает дату 18-м веке в форматы чисел стандартного и старого стиля для шрифта Palatino Linotype.  
  
 ![Текст, использующий старый стиль числа OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont24.png "OpenTypeFont24")  
Текст, использующий старый стиль числа OpenType  
  
 Следующий текст отображает стандартные числа для шрифта Palatino Linotype, за которыми следуют числа старого стиля.  
  
 ![Текст, использующий OpenType наборы чисел старого стиля](../../../../docs/framework/wpf/advanced/media/opentypefont13.png "opentypefont13")  
Текст, использующий наборы чисел старого стиля OpenType  
  
 В следующем примере разметки показано определение чисел старого стиля для шрифта Palatino Linotype с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>Пропорциональные и табличные цифры  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]шрифты поддерживают отображение пропорциональных и табличных цифр для регулирования выравнивания по ширине при использовании чисел. Пропорциональные цифры считать каждого цифру со своей шириной — «1» будет уже, чем «5». Табличные цифры рассматриваются как цифры равной ширины, что выравнивает их по вертикали, повышает удобочитаемость финансовой информации.  
  
 Приведенный ниже текст отображает две пропорциональные цифры в первом столбце с использованием шрифта Miramonte. Обратите внимание на разницу в ширине между цифрами «5» и «1». Во втором столбце показаны же два числовых значения с шириной, скорректированной с помощью функции табличных цифр.  
  
 ![Текст, использующий пропорциональные & табличные цифры OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont22.png "OpenTypeFont22")  
Текст, использующий пропорциональные и табличные цифры OpenType  
  
 В следующем примере разметки показано определение пропорциональные и табличные цифры для шрифта Miramonte с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>Нуль  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]шрифты поддерживают перечеркнутого нуля формат чисел, чтобы подчеркнуть разницу между буквой «O» и цифрой «0». Перечеркнутый ноль часто используется для идентификаторов в финансовых и деловых сведений.  
  
 Приведенный ниже текст отображает пример идентификатора заказа при помощи шрифта Miramonte. Первая строка использует стандартные цифры. Во второй строке используются перечеркнутые нули, чтобы подчеркнуть с заглавной буквы «O».  
  
 ![Текст, использующий OpenType перечеркнутые нули](../../../../docs/framework/wpf/advanced/media/opentypefont17.png "OpenTypeFont17")  
Текст, использующий перечеркнутые нули OpenType  
  
 В следующем примере разметки показано определение перечеркнутого нуля для шрифта Miramonte с помощью свойств <xref:System.Windows.Documents.Typography> объекта.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a>Класс оформления  
 <xref:System.Windows.Documents.Typography> объект предоставляет набор функций, [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] поддерживает шрифт. Задав свойства <xref:System.Windows.Documents.Typography> в разметке, можно легко создавать документы, которые используют преимущества [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] функции.  
  
 Приведенный ниже текст отображает стандартные прописных букв для шрифта Pescadero следуют буквы, в стиле «Малые прописные» и «AllSmallCaps». В этом случае для всех трех слов используется тот же размер шрифта.  
  
 ![Текст, использующий прописные буквы OpenType](../../../../docs/framework/wpf/advanced/media/opentypefont11.png "opentypefont11")  
Текст, использующий прописные буквы OpenType  
  
 В следующем примере разметки показано определение прописных букв для шрифта Pescadero с помощью свойств <xref:System.Windows.Documents.Typography> объекта. При использовании формата «Малые прописные» начальные прописные буквы учитывается.  
  
 [!code-xml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 В следующем примере кода выполняет ту же задачу, что и предыдущий пример разметки.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>Класс свойств оформления  
 В следующей таблице перечислены свойства, значения и параметры по умолчанию <xref:System.Windows.Documents.Typography> объекта.  
  
|Свойство|Значения|Значение по умолчанию|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|Числовое значение — байт|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals>|<xref:System.Windows.FontCapitals?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|Числовое значение — байт|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage>|<xref:System.Windows.FontEastAsianLanguage?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths>|<xref:System.Windows.FontEastAsianWidths?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction> | <xref:System.Windows.FontFraction> | <xref:System.Windows.FontFraction>|<xref:System.Windows.FontFraction?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment> | <xref:System.Windows.FontNumeralAlignment> | <xref:System.Windows.FontNumeralAlignment>|<xref:System.Windows.FontNumeralAlignment?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|числовое значение — байт|0|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|числовое значение — байт|0|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants>|<xref:System.Windows.FontVariants?displayProperty=fullName>|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Documents.Typography>   
 [Спецификация OpenType](http://go.microsoft.com/fwlink/?LinkId=96731)   
 [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Образец пакета шрифтов OpenType](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)   
 [Упаковка шрифтов с приложениями](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)