---
title: Дополнительное форматирование текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
ms.openlocfilehash: 59ae3173eaeda6681f76ca28ef060dd963a4e1a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="advanced-text-formatting"></a>Дополнительное форматирование текста
Windows Presentation Foundation (WPF) предоставляет широкий набор [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] для включения текста в приложении. Макет и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], такие как <xref:System.Windows.Controls.TextBlock>, обеспечивают наиболее распространенные и использовать общие элементы для представления текста. Рисование [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], такие как <xref:System.Windows.Media.GlyphRunDrawing> и <xref:System.Windows.Media.FormattedText>, предоставляют средства для включения в рисунки форматированного текста. Наиболее продвинутом уровне [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет расширяемый механизм форматирования текста для управления каждым аспектом представления текста: управление хранением, исполнением форматирования текста и внедренного объекта управления.  
  
 В этом разделе содержатся вводные [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] форматирование текста. Этот раздел посвящен реализации клиента и использовании [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] процессор форматирования текста.  
  
> [!NOTE]
>  Все примеры кода в этот документ можно найти в [расширенный пример форматирование текста](http://go.microsoft.com/fwlink/?LinkID=159965).  
  

  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 В этом разделе предполагается, что вы знакомы с высоким уровнем [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] используется для представления текста. Большинство пользовательских скриптов не потребует дополнительного форматирования текста [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] рассматриваются в данном разделе. Введение в другой текстовой [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], в разделе [документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
<a name="section1"></a>   
## <a name="advanced-text-formatting"></a>Дополнительное форматирование текста  
 Макет текста и [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] элементы управления в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляют свойства форматирования, позволяющие легко включать в приложение форматированный текст. Эти элементы управления предоставляют ряд свойств для обработки представления текста, включая гарнитуру, размер и цвет. В обычных условиях эти элементы управления могут обрабатывать большинство вариантов представления текста в приложении. Тем не менее некоторые расширенные сценарии требуют управления хранением текста, а также его представлением. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет расширяемый механизм форматирования текста для этой цели.  
  
 Найти дополнительные функции форматирования текста в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] состоят из механизма форматирования, текстовому хранилищу отрезками текста и свойств форматирования текста. Процессор, форматирования текста <xref:System.Windows.Media.TextFormatting.TextFormatter>, создает строки текста, используемый для представления. Это достигается путем запуска процесса форматирования строки и вызовом модуля форматирования текста <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>. Модуль форматирования текста извлекает отрезками текста из текстового хранилища путем вызова в хранилище <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> метод. <xref:System.Windows.Media.TextFormatting.TextRun> Объекты затем формируются в <xref:System.Windows.Media.TextFormatting.TextLine> объектов модулем форматирования текста и передаются в приложение для проверки или отображения.  
  
<a name="section2"></a>   
## <a name="using-the-text-formatter"></a>Использование модуля форматирования текста  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> — [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] модуль форматирования текста и предоставляет службы для форматирования и разбивки текста на строки. Модуль форматирования текста может обрабатывать различные форматы текстовых символов и стили абзацев и включает поддержку международного макета текста.  
  
 В отличие от традиционного текстового [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], <xref:System.Windows.Media.TextFormatting.TextFormatter> взаимодействует с клиентом разметки текста через набор методов обратного вызова. Требуется клиент для предоставления этих методов в реализации <xref:System.Windows.Media.TextFormatting.TextSource> класса. На следующей схеме показано взаимодействие разметки текста между клиентским приложением и <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Схема клиента структуры текста и TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Взаимодействие между приложением и TextFormatter  
  
 Модуль форматирования текста используется для извлечения форматированных строк текста из хранилища текста, который является реализацией <xref:System.Windows.Media.TextFormatting.TextSource>. Это делается путем создания экземпляра модуля форматирования текста с помощью <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> метод. Этот метод создает экземпляр модуля форматирования текста и задает максимальные значения высоты и ширины строки. Как только создается экземпляр модуля форматирования текста, процесс создания строки запускается вызовом <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> метод. <xref:System.Windows.Media.TextFormatting.TextFormatter> Осуществляет обратный вызов для получения текста и параметры форматирования для блоков текста с исходным текстом этой формы строки.  
  
 В следующем примере показан процесс форматирования хранилища текста. <xref:System.Windows.Media.TextFormatting.TextFormatter> Объект используется для извлечения строк текста из хранилища текста и затем отформатировать строку текста для рисования в <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[TextFormatterExample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## <a name="implementing-the-client-text-store"></a>Реализация клиентского хранилища текста  
 При расширении механизма форматирования текста необходимо реализовать все аспекты хранилища текста и управлять ими. Это довольно сложная задача. Хранилище текста отвечает за отслеживание свойств фрагментов текста, свойств абзаца, встроенных объектов и других подобных элементов. Он также предоставляет модуль форматирования текста с отдельными <xref:System.Windows.Media.TextFormatting.TextRun> объекты, которые использует модуль форматирования текста для создания <xref:System.Windows.Media.TextFormatting.TextLine> объектов.  
  
 Для виртуализации хранилища текста, хранилище текста должен быть производным от <xref:System.Windows.Media.TextFormatting.TextSource>. <xref:System.Windows.Media.TextFormatting.TextSource> Задает метод, используемый модулем форматирования текста для извлечения текстовых последовательностей из хранилища текста. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> Представляет метод, используемый модулем форматирования текста для извлечения текста последовательностей, используемых в форматировании строки. Вызов <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> неоднократно осуществляется модулем форматирования текста, пока не произойдет одно из следующих условий:  
  
-   Объект <xref:System.Windows.Media.TextFormatting.TextEndOfLine> или возвращаемых подкласс.  
  
-   Суммарная ширина отрезками текста превышает ширину строк, указанную в вызов для создания модуля форматирования текста или вызова для форматирования текста <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> метод.  
  
-   Объект [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] возвращается последовательность знаков, например «CF», «CRLF» или «LF».  
  
<a name="section4"></a>   
## <a name="providing-text-runs"></a>Предоставление фрагментов текста  
 Ядром процесса форматирования текста является взаимодействие между модулем форматирования текста и хранилищем текста. Реализация <xref:System.Windows.Media.TextFormatting.TextSource> предоставляет модуль форматирования текста с <xref:System.Windows.Media.TextFormatting.TextRun> объектов и свойств, с которыми форматируются исполнения текста. Это взаимодействие обрабатывается <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> метод, который вызывается модулем форматирования текста.  
  
 В следующей таблице приведены некоторые из предварительно определенных <xref:System.Windows.Media.TextFormatting.TextRun> объектов.  
  
|Тип TextRun|Использование|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Специализированный фрагмент текста, который используется для передачи представления глифов символов обратно в модуль форматирования текста.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Специализированный фрагмент текста, который используется для предоставления содержимого, в котором измерение, проверка нажатия и рисование выполняются в целом (например, кнопка или изображение в тексте).|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Специализированный фрагмент текста, который используется для обозначения конца строки.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Специализированный фрагмент текста, который используется для обозначения конца абзаца.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Специализированное исполнение текста используется для обозначения конца сегмента, такие как конец области, затронутых предыдущим <xref:System.Windows.Media.TextFormatting.TextModifier> запуска.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Специализированный фрагмент текста, который используется для отметки диапазона скрытых символов.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Специализированный фрагмент текста, который используется для изменения свойств фрагментов текста в своей области. Область расширяется до следующего соответствия <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> отрезка текста или следующей <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>.|  
  
 Готовых <xref:System.Windows.Media.TextFormatting.TextRun> объектов может быть подклассом. Это позволяет источнику текста предоставлять модуль форматирования текста с фрагментами текста, включающими пользовательские данные.  
  
 В следующем примере демонстрируется <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> метод. Этот хранилище текста возвращает <xref:System.Windows.Media.TextFormatting.TextRun> объектов для форматирования текста для обработки.  
  
 [!code-csharp[TextFormatterExample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
>  В этом примере хранилище текста предоставляет одни и те же свойства текста всему тексту. Расширенные хранилища текста могут потребоваться для реализации собственного управления диапазонами, чтобы позволить отдельным символам иметь разные свойства.  
  
<a name="section5"></a>   
## <a name="specifying-formatting-properties"></a>Задание свойств форматирования  
 <xref:System.Windows.Media.TextFormatting.TextRun> объекты форматируются с помощью свойств, предоставляемых хранилищем текста. Эти свойства делятся на два типа <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> и <xref:System.Windows.Media.TextFormatting.TextRunProperties>. <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> обрабатывает внутренние свойства параграфа, таких как <xref:System.Windows.TextAlignment> и <xref:System.Windows.FlowDirection>. <xref:System.Windows.Media.TextFormatting.TextRunProperties> являются свойствами, которые могут быть разными для каждого запуска в пределах абзаца, таких как кисть переднего плана текста <xref:System.Windows.Media.Typeface>и размер шрифта. Для реализации пользовательских абзацев и типы свойств пользовательского текста, приложение должно создать классы, производные от <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> и <xref:System.Windows.Media.TextFormatting.TextRunProperties> соответственно.  
  
## <a name="see-also"></a>См. также  
 [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
