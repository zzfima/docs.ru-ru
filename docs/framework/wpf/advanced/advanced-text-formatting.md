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
ms.openlocfilehash: 745d20e0bd4f877f9d4559f9fc7829b56689d35c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185941"
---
# <a name="advanced-text-formatting"></a>Дополнительное форматирование текста
Фонд презентации Windows (WPF) предоставляет надежный набор AA для включения текста в приложение. Layout [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] и AA, <xref:System.Windows.Controls.TextBlock>такие как, обеспечивают наиболее распространенные и общие элементы для представления текста. Рисование <xref:System.Windows.Media.GlyphRunDrawing> AIS, <xref:System.Windows.Media.FormattedText>например, и, обеспечивает средство для включения отформатированный текст в чертежи. На самом продвинутом уровне WPF предоставляет расширенный движок форматирования текста для управления каждым аспектом текстового представления, таким как управление текстовым магазином, управление форматированием текстовых запусков и управление встроенными объектами.  
  
 Эта тема содержит введение в формат текста WPF. Основное внимание уделяется реализации и использованию движка форматирования текста WPF.  
  
> [!NOTE]
> Все примеры кода в этом документе можно найти в [продвинутом примере форматирования текста.](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI/TextFormatting)  

<a name="prereq"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Эта тема предполагает, что вы знакомы с AA, используемыми для представления текста более высокого уровня. Большинство пользовательских сценариев не потребует расширенного форматирования текста AIS, обсуждаемых в этой теме. Для введения в различные AI текста, [см.](documents-in-wpf.md)  
  
<a name="section1"></a>
## <a name="advanced-text-formatting"></a>Дополнительное форматирование текста  
 Текстовый макет [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] и элементы управления в WPF обеспечивают свойства форматирования, которые позволяют легко включать отформатированный текст в приложение. Эти элементы управления предоставляют ряд свойств для обработки представления текста, включая гарнитуру, размер и цвет. В обычных условиях эти элементы управления могут обрабатывать большинство вариантов представления текста в приложении. Тем не менее некоторые расширенные сценарии требуют управления хранением текста, а также его представлением. WPF предоставляет для этой цели расширяемый механизм форматирования текста.  
  
 Расширенные функции форматирования текста, найденные в WPF, состоят из движка форматирования текста, текстового хранилища, текстовых запусков и свойств форматирования. Текст форматирования двигателя, <xref:System.Windows.Media.TextFormatting.TextFormatter>, создает строки текста, которые будут использоваться для презентации. Это достигается путем иначины процесса форматирования строки и <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>вызова текста formatter's . Текст formatter извлекает текст, выражающийся из <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> текстового хранилища, позвонив в метод магазина. Объекты <xref:System.Windows.Media.TextFormatting.TextRun> затем формируются в <xref:System.Windows.Media.TextFormatting.TextLine> объекты по тексту formatter и отдаются вашему приложению для проверки или отображения.  
  
<a name="section2"></a>
## <a name="using-the-text-formatter"></a>Использование модуля форматирования текста  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>является движком форматирования текста WPF и предоставляет услуги по форматированию и нарушению текстовых строк. Модуль форматирования текста может обрабатывать различные форматы текстовых символов и стили абзацев и включает поддержку международного макета текста.  
  
 В отличие от традиционного <xref:System.Windows.Media.TextFormatting.TextFormatter> API текста, он взаимодействует с клиентом макета текста через набор методов обратного вызова. Это требует от клиента предоставить эти методы в реализации <xref:System.Windows.Media.TextFormatting.TextSource> класса. Следующая диаграмма иллюстрирует взаимодействие макета текста между <xref:System.Windows.Media.TextFormatting.TextFormatter>клиентским приложением и .  
  
 ![Схема клиента структуры текста и TextFormatter](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 Текстная стоимость используется для извлечения отформатированных текстовых строк <xref:System.Windows.Media.TextFormatting.TextSource>из текстового хранилища, что является реализацией . Это делается путем создания экземпляра текстовой <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> материи с помощью метода. Этот метод создает экземпляр модуля форматирования текста и задает максимальные значения высоты и ширины строки. Как только экземпляр formatter текста создается, процесс создания строки <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> запускается путем вызова метода. <xref:System.Windows.Media.TextFormatting.TextFormatter>вызывает обратно в источник текста, чтобы получить текст и параметры форматирования для запусков текста, которые образуют строку.  
  
 В следующем примере показан процесс форматирования хранилища текста. Объект <xref:System.Windows.Media.TextFormatting.TextFormatter> используется для извлечения текстовых строк из текстового хранилища, <xref:System.Windows.Media.DrawingContext>а затем форматировать текстовую строку для втягивания в .  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>
## <a name="implementing-the-client-text-store"></a>Реализация клиентского хранилища текста  
 При расширении механизма форматирования текста необходимо реализовать все аспекты хранилища текста и управлять ими. Это довольно сложная задача. Хранилище текста отвечает за отслеживание свойств фрагментов текста, свойств абзаца, встроенных объектов и других подобных элементов. Он также предоставляет текстовое <xref:System.Windows.Media.TextFormatting.TextRun> вещество с отдельными объектами, которые текст formatter использует для создания <xref:System.Windows.Media.TextFormatting.TextLine> объектов.  
  
 Для обработки виртуализации текстового хранилища, <xref:System.Windows.Media.TextFormatting.TextSource>текстовый магазин должен быть получен из . <xref:System.Windows.Media.TextFormatting.TextSource>определяет метод, используемый текстом для извлечения текста из хранилища текста. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>— это метод, используемый текстовой подачей для извлечения текстовых запусков, используемых при форматировании строк. Призыв к <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> неоднократно издавался текстовой номером до тех пор, пока не возникнет одно из следующих условий:  
  
- A <xref:System.Windows.Media.TextFormatting.TextEndOfLine> или возвращается подкласс.  
  
- Накопленная ширина текстовых запусков превышает максимальную ширину строки, указанную либо в вызове <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> для создания частоты текста, либо в вызове к методу текстовой магистрали.  
  
- Возвращается новая последовательность Unicode, например "CF", "LF" или "CRLF".  
  
<a name="section4"></a>
## <a name="providing-text-runs"></a>Предоставление фрагментов текста  
 Ядром процесса форматирования текста является взаимодействие между модулем форматирования текста и хранилищем текста. Ваша реализация <xref:System.Windows.Media.TextFormatting.TextSource> обеспечивает текст formatter <xref:System.Windows.Media.TextFormatting.TextRun> с объектами и свойствами, с которыми для формата текста работает. Это взаимодействие обрабатывается <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> методом, который называется текстом formatter.  
  
 В следующей таблице показаны <xref:System.Windows.Media.TextFormatting.TextRun> некоторые предопределенные объекты.  
  
|Тип TextRun|Использование|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Специализированный фрагмент текста, который используется для передачи представления глифов символов обратно в модуль форматирования текста.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Специализированный фрагмент текста, который используется для предоставления содержимого, в котором измерение, проверка нажатия и рисование выполняются в целом (например, кнопка или изображение в тексте).|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Специализированный фрагмент текста, который используется для обозначения конца строки.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Специализированный фрагмент текста, который используется для обозначения конца абзаца.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Специализированный текстовый запуск, используемый для обозначения конца сегмента, <xref:System.Windows.Media.TextFormatting.TextModifier> например, для окончания области, затрагиваемый предыдущим запуском.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Специализированный фрагмент текста, который используется для отметки диапазона скрытых символов.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Специализированный фрагмент текста, который используется для изменения свойств фрагментов текста в своей области. Область распространяется на следующий <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> соответствующий текст <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>запуска, или следующий .|  
  
 Любой из <xref:System.Windows.Media.TextFormatting.TextRun> предопределенных объектов может быть подклассифицирован. Это позволяет источнику текста предоставлять модуль форматирования текста с фрагментами текста, включающими пользовательские данные.  
  
 В следующем примере <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> показан метод. Этот текстовый <xref:System.Windows.Media.TextFormatting.TextRun> магазин возвращает объекты в текстовое значение для обработки.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> В этом примере хранилище текста предоставляет одни и те же свойства текста всему тексту. Расширенные хранилища текста могут потребоваться для реализации собственного управления диапазонами, чтобы позволить отдельным символам иметь разные свойства.  
  
<a name="section5"></a>
## <a name="specifying-formatting-properties"></a>Задание свойств форматирования  
 <xref:System.Windows.Media.TextFormatting.TextRun>объекты отформатированы с помощью свойств, предоставляемых текстовым хранилищем. Эти свойства бывают двух <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> <xref:System.Windows.Media.TextFormatting.TextRunProperties>типов, и . <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>обрабатывать абзац <xref:System.Windows.TextAlignment> инклюзивных свойств, таких как и <xref:System.Windows.FlowDirection>. <xref:System.Windows.Media.TextFormatting.TextRunProperties>свойства, которые могут быть различными для каждого текста, запускаемого в абзаце, такие как кисть <xref:System.Windows.Media.Typeface>переднего плана и размер шрифта. Для реализации пользовательских типов свойств запуска текста и пользовательского текста приложение должно создавать классы, которые вытекают из <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> и <xref:System.Windows.Media.TextFormatting.TextRunProperties> соответственно.  
  
## <a name="see-also"></a>См. также раздел

- [Оформление в WPF](typography-in-wpf.md)
- [Документы в WPF](documents-in-wpf.md)
