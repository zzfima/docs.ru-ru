---
title: "Удаление добавляемого конструктором в файл XAML состояния просмотра | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Удаление добавляемого конструктором в файл XAML состояния просмотра
Этот образец демонстрирует создание класса, производного от <xref:System.Windows.Markup.XamlWriter>, и удаление состояния представления из файла XAML.[!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] записывает сведения в документ XAML, который известен как состояние представления.Состоянием представления называются сведения, которые требуются во время разработки, такие как расположение макета, и не требуются во время выполнения.[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] вставляет эти сведения в документ XAML в ходе внесения в него изменений.[!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] записывает состояние представления в файл XAML с атрибутом `mc:Ignorable`, поэтому эти сведения не загружаются, когда среда выполнения загружает файл XAML.Этот образец демонстрирует, как создать класс, который удаляет указанные сведения о состоянии представления при обработке узлов XAML.  
  
## Обсуждение  
 Этот образец демонстрирует создание пользовательского модуля записи.  
  
 Чтобы сформировать пользовательский модуль записи XAML, создайте класс, который наследует от <xref:System.Windows.Markup.XamlWriter>.Модули записи XAML часто бывают вложенными, поэтому обычно отслеживается «внутренний» модуль записи XAML.Эти «внутренние» модули записи могут рассматриваться как ссылка на стек остальных модулей записи XAML, что позволяет получить несколько точек входа для выполнения работы, а затем делегировать обработку остальной части стека.  
  
 В этом образце есть несколько особенностей, представляющих интерес.Одна из них состоит в том, что проводится проверка для определения принадлежности записываемого элемента пространству имен конструктора.Обратите внимание на то, что при этом исключается также использование других типов из пространства имен конструктора в рабочем процессе.  
  
```  
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)  
{  
return xamlMember.IsAttachable &&  
   xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);  
}  
  
const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";  
The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.  
public ViewStateCleaningWriter(XamlWriter innerWriter)  
{  
this.InnerWriter = innerWriter;  
this.MemberStack = new Stack<XamlMember>();  
}  
  
XamlWriter InnerWriter {get; set; }  
Stack<XamlMember> MemberStack {get; set; }  
  
```  
  
 Кроме того, при этом создается стек элементов XAML, которые используются при прохождении потока узла.Остальная часть работы в этом образце в основном выполняется в методе <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>.  
  
```  
public override void WriteStartMember(XamlMember xamlMember)  
{  
MemberStack.Push(xamlMember);  
if (IsDesignerAttachedProperty(xamlMember))  
{  
m_attachedPropertyDepth++;  
}  
  
if (m_attachedPropertyDepth > 0)  
{  
return;  
}  
  
InnerWriter.WriteStartMember(xamlMember);  
}  
  
```  
  
 Затем последующие методы проверяют, содержатся ли до сих пор в контейнере состояния представления, и в случае положительного ответа выполняют возврат, а не передают узел в направлении к нижней части стека модулей записи.  
  
```  
public override void WriteValue(Object value)  
{  
if (m_attachedPropertyDepth > 0)  
{  
return;  
}  
  
InnerWriter.WriteValue(value);  
}  
```  
  
 Чтобы использовать пользовательский модуль записи XAML, необходимо соединить его вместе с другими в стеке модулей записи XAML.В следующем коде показано, как это можно использовать.  
  
```  
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };  
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);  
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());  
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);  
  
```  
  
#### Использование этого образца  
  
1.  Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения ViewStateCleaningWriter.sln.  
  
2.  Откройте окно командной строки и перейдите к каталогу, в котором сформирован файл ViewStageCleaningWriter.exe.  
  
3.  Запустите ViewStateCleaningWriter.exe применительно к файлу Workflow1.xaml.  
  
     Синтаксис для этого исполняемого файла показан в следующем примере.  
  
 **ViewStateCleaningWriter.exe \[входной файл\] \[выходной файл\]**     При этом происходит вывод файла XAML в \[выходной файл\], в котором удалена вся имеющаяся информация о состоянии представления.  
  
    > [!NOTE]
    >  Что касается рабочего процесса <xref:System.Activities.Statements.Sequence>, то удаляется целый ряд подсказок виртуализации.Это вынуждает конструктор повторно вычислять макет при его следующей загрузке.При использовании этого образца для <xref:System.Activities.Statements.Flowchart> удаляется вся информация о расположении и маршрутизации линий, а при последующей загрузке в конструктор все действия отображаются в левой стороне экрана с наложением друг на друга.  
  
#### Создание образца файл XAML для использования с этим образцом  
  
1.  Откройте [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Создайте новое консольное приложение рабочего процесса.  
  
3.  Перетащите на полотно несколько действий  
  
4.  Сохраните файл XAML рабочего процесса.  
  
5.  Изучите файл XAML, чтобы видеть свойства, закрепленные за состоянием представления.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`  
  
## См. также