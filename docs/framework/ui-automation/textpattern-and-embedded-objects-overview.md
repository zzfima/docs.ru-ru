---
title: "TextPattern and Embedded Objects Overview | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "UI Automation, TextPattern class"
  - "embedded objects, accessing"
  - "accessing embedded objects"
  - "embedded objects, UI Automation"
ms.assetid: 93fdfbb9-0025-4b72-8ca0-0714adbb70d5
caps.latest.revision: 17
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 17
---
# TextPattern and Embedded Objects Overview
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], заданные в пространстве имен <xref:System.Windows.Automation>. Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом обзоре описано, как [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] представляет внедренные объекты или дочерние элементы в текстовом документе или контейнере.  
  
 В [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] внедренный объект — это любой элемент, содержащий нетекстовые границы, например изображение, гиперссылка, таблица, электронная таблица [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] или файл [!INCLUDE[TLA#tla_winmedia](../../../includes/tlasharptla-winmedia-md.md)]. Это отличается от стандартного определения, где элемент создается в одном приложении и внедряется или связывается в другом. То, может ли объект редактироваться в его исходном приложении, не важно в контексте [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Embedded_Objects_and_the_UI_Automation_Tree"></a>   
## Внедренные объекты и дерево модели автоматизации пользовательского интерфейса  
 Внедренные объекты рассматриваются как отдельные элементы в представлении элементов управления дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Они представляются как дочерние элементы контейнера текста, чтобы доступ к ним можно было получать с помощью той же модели, как и для других элементов управления в [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
 ![Вставленная таблица с изображением в текстовом контейнере](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-example1.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_Example1")  
Пример контейнера текста внедренными объектами таблицы, изображения и гиперссылки  
  
 ![Просмотр содержимого предыдущего примера](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-example2.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_Example2")  
Пример представления содержимого для части предыдущего контейнера текста  
  
<a name="Expose_Embedded_Objects_Using_TextPattern_and"></a>   
## Предоставление внедренных объектов с помощью TextPattern и TextPatternRange  
 Используемые в сочетании, класс шаблона элемента управления <xref:System.Windows.Automation.TextPattern> и класс <xref:System.Windows.Automation.Text.TextPatternRange> предоставляют методы и свойства, упрощающие навигацию и запросы внедренных объектов.  
  
 Текстовое содержимое \(или внутренний текст\) контейнера текста и внедренного объекта, например гиперссылки или ячейки таблицы, представляется как один непрерывный текстовый поток и в представлении элемента управления и в представлении содержимого дерева [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Границы объекта игнорируются. Если клиент автоматизации пользовательского интерфейса извлекает текст с целью вывода, интерпретации или анализа, текстовый диапазон следует проверить на соответствие особым случаям, например таблице с текстовым содержимым или другим внедренным объектам. Для этого можно вызвать <xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>, чтобы получить <xref:System.Windows.Automation.AutomationElement> для каждого внедренного объекта, и затем вызвать <xref:System.Windows.Automation.TextPattern.RangeFromChild%2A>, чтобы получить текстовый диапазон для каждого элемента. Это выполняется рекурсивно, пока не будет получено все текстовое содержимое.  
  
 ![Текст, разделенный вставленными объектами.](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjecttextranges.png "UIA\_TextPattern\_EmbeddedObjectTextRanges")  
Пример текстового потока с внедренными объектами и их диапазонами  
  
 Для обхода содержимого текстового диапазона в фоновом режиме применяется ряд шагов для успешного выполнения метода <xref:System.Windows.Automation.Text.TextPatternRange.Move%2A>.  
  
1.  Текстовый диапазон нормализован, т. е. он свернут до вырожденного диапазона в конечной точке <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint>, что делает конечную точку <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint> избыточной. Этот шаг необходим для устранения неоднозначности в случаях, когда текстовый диапазон охватывает границы <xref:System.Windows.Automation.Text.TextUnit>, например: "{U}RL\-адрес [http:\/\/www.microsoft.com](http://www.microsoft.com) внедряется в текст" где "{" и "}" — конечные точки диапазона текста.  
  
2.  Результирующий диапазон перемещается в <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> в начало запрошенной границы <xref:System.Windows.Automation.Text.TextUnit>.  
  
3.  Диапазон перемещается вперед или назад в <xref:System.Windows.Automation.TextPattern.DocumentRange%2A> на запрошенное число границ <xref:System.Windows.Automation.Text.TextUnit>.  
  
4.  Затем диапазон расширяется из вырожденного состояния путем перемещения конечной точки <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint> на одну запрошенную границу <xref:System.Windows.Automation.Text.TextUnit>.  
  
 ![Настройка диапазона при помощи Move & ExpandToEnclosingUnit](../../../docs/framework/ui-automation/media/uia-textpattern-moveandexpand-examples.png "UIA\_TextPattern\_MoveAndExpand\_Examples")  
Примеры корректировки текстового диапазона для Move\(\) и ExpandToEnclosingUnit\(\)  
  
<a name="Common_Scenarios"></a>   
## Стандартные сценарии  
 В следующих разделах представлены примеры наиболее распространенных сценариев, использующих внедренные объекты.  
  
 Условные обозначения для приведенных примеров:  
  
 { \= <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint>  
  
 } \= <xref:System.Windows.Automation.Text.TextPatternRangeEndpoint>  
  
<a name="Hyperlink"></a>   
### Гиперссылка  
 **Пример 1. Текстовый диапазон, содержащий внедренную текстовую гиперссылку**  
  
 {URL\-адрес [http:\/\/www.microsoft.com](http://www.microsoft.com) внедряется в текст}.  
  
|Вызываемый метод|Результат|  
|----------------------|---------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Возвращает строку "URL\-адрес http:\/\/www.microsoft.com внедряется в текст".|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Возвращает внутренний <xref:System.Windows.Automation.AutomationElement>, который охватывает диапазон текста. В этом случае это <xref:System.Windows.Automation.AutomationElement>, представляющий поставщик текста.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Возвращает <xref:System.Windows.Automation.AutomationElement>, представляющий элемент управления гиперссылки.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A>, где <xref:System.Windows.Automation.AutomationElement> — это объект, возвращаемый предыдущим методом `GetChildren`.|Возвращает диапазон, представляющий "http:\/\/www.microsoft.com".|  
  
 **Пример 2. Текстовый диапазон, частично охватывающий внедренную текстовую гиперссылку**  
  
 URL\-адрес http:\/\/{[www](www)} внедрен в текст.  
  
|Вызываемый метод|Результат|  
|----------------------|---------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Возвращает строку "www".|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Возвращает внутренний <xref:System.Windows.Automation.AutomationElement>, который охватывает диапазон текста. В этом случае это элемент управления гиперссылки.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Возвращает, `null` так как диапазон текста не охватывает всю строку URL\-адреса.|  
  
 **Пример 3. Текстовый диапазон, частично охватывающий содержимое контейнера текста. Контейнер текста содержит внедренную текстовую гиперссылку, которая не является частью текстового диапазона.**  
  
 {URL\-адрес} [http:\/\/www.microsoft.com](http://www.microsoft.com) внедряется в текст.  
  
|Вызываемый метод|Результат|  
|----------------------|---------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Возвращает строку "URL\-адрес".|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Возвращает внутренний <xref:System.Windows.Automation.AutomationElement>, который охватывает диапазон текста. В этом случае это <xref:System.Windows.Automation.AutomationElement>, представляющий поставщик текста.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> с параметрами \(TextUnit.Word, 1\).|Перемещает занимаемый диапазон текста к "http", так как текст гиперссылки состоит из отдельных слов. В этом случае гиперссылка не рассматривается как один объект.<br /><br /> URL\-адрес {[http](../../../ocs/framework/network-programming/http.md)} внедряется в текст.|  
  
<a name="Image"></a>   
### Изображение  
 **Пример 1. Текстовый диапазон, содержащий внедренное изображение**  
  
 {Изображение ![Пример вставленного изображения](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-imageexample.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_ImageExample") внедрено в текст}.  
  
|Вызываемый метод|Результат|  
|----------------------|---------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Возвращает строку "внедрено в текст". Любой замещающий текст, связанный с изображением, не может быть включен в текстовый поток.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Возвращает внутренний <xref:System.Windows.Automation.AutomationElement>, который охватывает диапазон текста. В этом случае это <xref:System.Windows.Automation.AutomationElement>, представляющий поставщик текста.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>|Возвращает <xref:System.Windows.Automation.AutomationElement>, представляющий элемент управления изображения.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A>, где <xref:System.Windows.Automation.AutomationElement> — это объект, возвращаемый предыдущим методом <xref:System.Windows.Automation.Text.TextPatternRange.GetChildren%2A>.|Возвращает вырожденный диапазон, представляющий "![Пример вставленного изображения](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-imageexample.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_ImageExample")".|  
  
 **Пример 2. Текстовый диапазон, частично охватывающий содержимое контейнера текста. Контейнер текста содержит внедренное изображение, которое не является частью текстового диапазона.**  
  
 {Изображение} ![Пример вставленного изображения](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-imageexample.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_ImageExample") внедрено в текст.  
  
|Вызываемый метод|Результат|  
|----------------------|---------------|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetText%2A>|Возвращает строку "Изображение".|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A>|Возвращает внутренний <xref:System.Windows.Automation.AutomationElement>, который охватывает диапазон текста. В этом случае это <xref:System.Windows.Automation.AutomationElement>, представляющий поставщик текста.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.Move%2A> с параметрами \(TextUnit.Word, 1\).|Перемещает текстовый диапазон к "is". Поскольку только основанные на тексте внедренные объекты считаются частью текстового потока, изображение в этом примере не влияет на перемещение или возвращаемое значение \(1 в данном случае\).|  
  
<a name="Table"></a>   
### Таблица  
  
### Таблица, используемая для примеров  
  
|Ячейка с изображением|Ячейка с текстом|  
|---------------------------|----------------------|  
|![Пример вставленного изображения](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-imageexample.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_ImageExample")|X|  
|![Пример 2 внедренного изображения](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-imageexample2.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_ImageExample2")|Y|  
|![Пример 3 внедренного изображения](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-imageexample3.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_ImageExample3")<br /><br /> Изображение для Z|Z|  
  
 **Пример 1. Получение контейнера текста из содержимого ячейки.**  
  
|Вызываемый метод|Результат|  
|----------------------|---------------|  
|<xref:System.Windows.Automation.GridPattern.GetItem%2A> с параметрами \(0,0\)|Возвращает <xref:System.Windows.Automation.AutomationElement>, представляющий содержимое ячейки таблицы. В этом случае элемент — это текстовый элемент управления.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A>, где <xref:System.Windows.Automation.AutomationElement> — это объект, возвращаемый предыдущим методом `GetItem`.|Возвращает диапазон, охватывающий изображение ![Пример вставленного изображения](../../../docs/framework/ui-automation/media/uia-textpattern-embedded-objects-overview-imageexample.png "UIA\_TextPattern\_Embedded\_Objects\_Overview\_ImageExample").|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> для объекта, возвращаемого предыдущим методом `RangeFromChild`.|Возвращает <xref:System.Windows.Automation.AutomationElement>, представляющий ячейку таблицы. В этом случае элемент — это текстовый элемент управления, поддерживающий TableItemPattern.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> для объекта, возвращаемого предыдущим методом `GetEnclosingElement`.|Возвращает <xref:System.Windows.Automation.AutomationElement>, представляющий таблицу.|  
|<xref:System.Windows.Automation.Text.TextPatternRange.GetEnclosingElement%2A> для объекта, возвращаемого предыдущим методом `GetEnclosingElement`.|Возвращает <xref:System.Windows.Automation.AutomationElement>, представляющий поставщик текста.|  
  
 **Пример 2. Получение текстового содержимого ячейки.**  
  
|Вызываемый метод|Результат|  
|----------------------|---------------|  
|<xref:System.Windows.Automation.GridPattern.GetItem%2A> с параметрами \(1,1\).|Возвращает <xref:System.Windows.Automation.AutomationElement>, представляющий содержимое ячейки таблицы. В этом случае элемент — это текстовый элемент управления.|  
|<xref:System.Windows.Automation.TextPattern.RangeFromChild%2A>, где <xref:System.Windows.Automation.AutomationElement> — это объект, возвращаемый предыдущим методом `GetItem`.|Возвращает "Y".|  
  
## См. также  
 <xref:System.Windows.Automation.TextPattern>   
 <xref:System.Windows.Automation.Text.TextPatternRange>   
 <xref:System.Windows.Automation.Provider.ITextProvider>   
 <xref:System.Windows.Automation.Provider.ITextRangeProvider>   
 [Access Embedded Objects Using UI Automation](../../../docs/framework/ui-automation/access-embedded-objects-using-ui-automation.md)   
 [Expose the Content of a Table Using UI Automation](../../../docs/framework/ui-automation/expose-the-content-of-a-table-using-ui-automation.md)   
 [Traverse Text Using UI Automation](../../../docs/framework/ui-automation/traverse-text-using-ui-automation.md)   
 [TextPattern Search and Selection Sample](http://msdn.microsoft.com/ru-ru/0a3bca57-8b72-489d-a57c-da85b7a22c7f)