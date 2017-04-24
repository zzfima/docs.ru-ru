---
title: "Дополнительное форматирование текста | Microsoft Docs"
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
  - "форматирование [WPF]"
  - "текст [WPF]"
  - "оформление, форматирование текста"
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Дополнительное форматирование текста
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] предоставляет [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] — набор надежных инструментов для включения текста в приложение.  Макет и [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], такие как <xref:System.Windows.Controls.TextBlock>, предоставляют наиболее типично и обще\-используемые элементы для представления текста.  [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] для рисования, например <xref:System.Windows.Media.GlyphRunDrawing> и <xref:System.Windows.Media.FormattedText>, предоставляют возможность включения в рисунки форматированного текста.  На наиболее продвинутом уровне [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет расширенный механизм форматирования текста для управления каждым аспектом представления текста: управление хранением и исполнением форматирования текста, и управление внедренным объектом.  
  
 В этом разделе представлено введение в форматирование текста [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  Основное внимание уделяется реализации клиента и использовании механизма форматирования текста [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
> [!NOTE]
>  Все примеры кода в этом документе можно найти в разделе [Пример расширенного форматирования текста](http://go.microsoft.com/fwlink/?LinkID=159965).  
  
   
  
<a name="prereq"></a>   
## Предварительные требования  
 Чтение этого раздела предполагает знакомство с верхним уровнем [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], использующегося для представлении текста.  Большинство пользовательских скриптов не потребует дополнительного форматирования текста [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], рассмотренного в этом разделе.  Для введения в другой текст [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] см. [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md).  
  
<a name="section1"></a>   
## Дополнительное форматирование текста  
 Макет текста и элементы управления [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляют свойства форматирования, позволяющие легко включать в приложение форматированный текст.  Эти элементы управления предоставляют ряд свойств для обработки представления текста, включающие его гарнитуру, размер и цвет.  В обычных условиях эти элементы управления могут обрабатывать большинство представлений текста в приложении.  Однако в некоторых более сложных ситуациях требуется контроль процесса хранения текста наравне с контролем представления.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] предоставляет для этой цели расширенный механизм форматирования текста.  
  
 Дополнительные функции форматирования текста, расположенные в [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], состоят из механизма форматирования текста, хранилища текста, исполнения текста и свойств форматирования.  Механизм форматирования текста, <xref:System.Windows.Media.TextFormatting.TextFormatter>, создает строки текста, используемые для его представления.  Это достигается путем инициирования процесса форматирования строки и вызовом модуля форматирования текста <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>.  Модуль форматирования текста извлекает текстовые последовательности из хранилища текста путем вызова метода хранения <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>.  Затем объекты <xref:System.Windows.Media.TextFormatting.TextRun> преобразуются в объекты <xref:System.Windows.Media.TextFormatting.TextLine> с помощью модуля форматирования текста и передаются в приложение для проверки или отображения на экране.  
  
<a name="section2"></a>   
## Использование модуля форматирования текста  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> является механизмом форматирования текста [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] и служит для форматирования и разбивки строк текста.  Модуль форматирования текста поддерживает различные форматы текстовых знаков и стили абзацев, а также включает поддержку международного макета текста.  
  
 В отличие от традиционного текстового [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], объект <xref:System.Windows.Media.TextFormatting.TextFormatter> взаимодействует с клиентом разметки текста через набор методов обратного вызова.  Для предоставления этих методов в реализации класса <xref:System.Windows.Media.TextFormatting.TextSource> требуется клиент.  Следующая диаграмма иллюстрирует взаимодействие разметки текста между клиентским приложением и объектом <xref:System.Windows.Media.TextFormatting.TextFormatter>.  
  
 ![Схема клиента структуры текста и TextFormatter](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
Взаимодействие между приложением и объектом TextFormatter  
  
 Модуль форматирования текста используется для извлечения форматированных строк текста из хранилища текста, которое является реализацией метода <xref:System.Windows.Media.TextFormatting.TextSource>.  Это осуществляется первоначальным созданием экземпляра модуля форматирования текста, путем использования метода <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A>.  Этот метод создает экземпляр модуля форматирования текста и задает максимальные значения высоты и ширины строки.  Как только экземпляр модуля форматирования текста создан, процесс создания строки запускается вызовом метода <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>.  Объект <xref:System.Windows.Media.TextFormatting.TextFormatter> выполняет обратный вызов метода к исходному тексту, чтобы извлечь текст и параметры форматирования для текстовых последовательностей, формирующих строку.  
  
 В следующем примере показан процесс форматирования хранилища текста.  Объект <xref:System.Windows.Media.TextFormatting.TextFormatter> используется для извлечения строк текста из хранилища текста и последующего форматирования строк текста для перемещения в <xref:System.Windows.Media.DrawingContext>.  
  
 [!code-csharp[TextFormatterExample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## Реализация клиентского хранилища текста  
 При расширении механизма форматирования текста потребуется реализовать и управлять аспектами хранилища текста.  Это нетривиальная задача.  Хранилище текста отвечает за отслеживание свойств исполнения текста, свойств абзаца, встроенных объектов и другого подобного содержимого.  Оно также предоставляет модуль форматирования текста с индивидуальными объектами <xref:System.Windows.Media.TextFormatting.TextRun>, которые модуль форматирования текста использует для создания объектов <xref:System.Windows.Media.TextFormatting.TextLine>.  
  
 Для виртуализации хранилища текста оно должно быть производным от класса <xref:System.Windows.Media.TextFormatting.TextSource>.  Объект <xref:System.Windows.Media.TextFormatting.TextSource> задает метод, используемый модулем форматирования текста для извлечения текстовых последовательностей из хранилища текста.  Метод <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> используется модулем форматирования текста для извлечения текстовых последовательностей, используемых в форматировании строки.  Вызов <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> неоднократно осуществляется модулем форматирования текста до тех пор, пока не выполняется одно из следующих условий:  
  
-   Возвращается <xref:System.Windows.Media.TextFormatting.TextEndOfLine> или подкласс.  
  
-   Суммарная ширина исполнений текста превышает ширину строк, указанную или в вызове для создания модуля форматирования текста или в вызове метода <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> модуля форматирования текста.  
  
-   Возвращается новая последовательность [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)], такая как «CF», «LF», или «CRLF».  
  
<a name="section4"></a>   
## Предоставление исполнений текста  
 Ядром процесса форматирования текста является взаимодействие между модулем форматирования текста и хранилищем текста.  Реализация <xref:System.Windows.Media.TextFormatting.TextSource> предоставляет модуля форматирования текста с объектами <xref:System.Windows.Media.TextFormatting.TextRun> и свойствами, с которыми форматируются исполнения текста.  Это взаимодействие обрабатывается методом <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>, который вызывается модулем форматирования текста.  
  
 В следующей таблице представлены некоторые из предварительно определенных объектов <xref:System.Windows.Media.TextFormatting.TextRun>.  
  
|Тип TextRun|Использование|  
|-----------------|-------------------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Специализированное исполнение текста, используемое для обратной передачи глифов символа модулю форматирования текста.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Специализированное исполнение текста используется для предоставления содержимого, в котором выполняются измерение, проверка наличия и рисование, такое как кнопка или изображения в тексте.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Специализированное исполнение текста используется для отметки конца строки.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Специализированное исполнение текста используется для отметки конца абзаца.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Специализированное исполнение текста используется для отметки конца сегмента, такого как конец области, на который влияет предыдущее исполнение <xref:System.Windows.Media.TextFormatting.TextModifier>.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Специализированное исполнение текста используется для отметки диапазона скрытых знаков.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Специализированное исполнение текста используется для изменения свойств исполнений текста в его области.  Область расширяется до следующего соответствия исполнению текста <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> или до следующего <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>.|  
  
 Любой из предварительно определенных объектов <xref:System.Windows.Media.TextFormatting.TextRun> может быть подклассом.  Это позволяет исходному тексту предоставлять модуль форматирования текста с исполнениями текста, включающими пользовательские данные.  
  
 В следующем примере демонстрируется использование метода <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>.  Этот хранилище текста возвращает объекты <xref:System.Windows.Media.TextFormatting.TextRun> модулю форматирования текста для обработки.  
  
 [!code-csharp[TextFormatterExample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
>  В этом примере, хранилище текста предоставляет те же свойства текста ко всему тексту.  Дополнительные хранилища текста потребуют реализации управления их собственным диапазоном для того, чтобы позволить индивидуальным знакам иметь различные свойства.  
  
<a name="section5"></a>   
## Определение свойств форматирования  
 Объекты <xref:System.Windows.Media.TextFormatting.TextRun> форматируются с помощью свойств, предоставляемых хранилищем текста.  Такие свойства бывают двух типов: <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> и <xref:System.Windows.Media.TextFormatting.TextRunProperties>.  Класс <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> обрабатывает внутренние свойства параграфа, например <xref:System.Windows.TextAlignment> и <xref:System.Windows.FlowDirection>.  Объект <xref:System.Windows.Media.TextFormatting.TextRunProperties> представляет свойства, которые могут отличаться для каждой текстовой последовательности внутри параграфа, например кисть переднего плана, <xref:System.Windows.Media.Typeface> и размер шрифта.  Для реализации пользовательских абзацев и пользовательских типов свойств исполнений текста, приложение должно создать классы, производные от <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> и <xref:System.Windows.Media.TextFormatting.TextRunProperties> соответственно.  
  
## См. также  
 [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)