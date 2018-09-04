---
title: Удаление добавляемого конструктором в файл XAML состояния просмотра
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: ed2fda0bb66b2c8fe58c60acc6f80b9e9c8e984e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524956"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a>Удаление добавляемого конструктором в файл XAML состояния просмотра
Этот образец демонстрирует создание класса, производного от <xref:System.Windows.Markup.XamlWriter>, и удаление состояния представления из файла XAML. [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] записывает сведения в документ XAML, который известен как состояние представления. Состоянием представления называются сведения, которые требуются во время разработки, такие как расположение макета, и не требуются во время выполнения. [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] вставляет эти сведения в документ XAML в ходе внесения в него изменений. [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] записывает состояние представления в файл XAML с атрибутом `mc:Ignorable`, поэтому эти сведения не загружаются, когда среда выполнения загружает файл XAML. Этот образец демонстрирует, как создать класс, который удаляет указанные сведения о состоянии представления при обработке узлов XAML.  
  
## <a name="discussion"></a>Обсуждение  
 Этот образец демонстрирует создание пользовательского модуля записи.  
  
 Чтобы сформировать пользовательский модуль записи XAML, создайте класс, который наследует от <xref:System.Windows.Markup.XamlWriter>. Как модули записи XAML часто бывают вложенными, он является типичным для отслеживания записи XAML «внутренние». Эти «внутреннее "модули записи могут рассматриваться как ссылка на стек остальных модулей записи XAML, что позволяет иметь несколько точек входа для выполнения работы, а затем делегировать обработку остальной части стека.  
  
 В этом образце есть несколько особенностей, представляющих интерес. Одна из них состоит в том, что проводится проверка для определения принадлежности записываемого элемента пространству имен конструктора. Обратите внимание на то, что при этом исключается также использование других типов из пространства имен конструктора в рабочем процессе.  
  
```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)  
{  
    return xamlMember.IsAttachable &&  
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);  
}  
  
const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";  

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.  
public ViewStateCleaningWriter(XamlWriter innerWriter)  
{  
    this.InnerWriter = innerWriter;  
    this.MemberStack = new Stack<XamlMember>();  
}  
  
XamlWriter InnerWriter {get; set; }  
Stack<XamlMember> MemberStack {get; set; }  
```  
  
 Кроме того, при этом создается стек элементов XAML, которые используются при прохождении потока узла. Остальная часть работы в этом образце во многом содержится в <!--zz  <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>--> `System.Windows.Markup.XamlWriter.WriteStartMember` метод.  
  
```csharp
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
  
```csharp
public override void WriteValue(Object value)  
{  
    if (m_attachedPropertyDepth > 0)  
    {  
        return;  
    }  
  
    InnerWriter.WriteValue(value);  
}  
```  
  
 Чтобы использовать пользовательский модуль записи XAML, необходимо соединить его вместе с другими в стеке модулей записи XAML. В следующем коде показано, как это можно использовать.  
  
```csharp 
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };  
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);  
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());  
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);  
```  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1. Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения ViewStateCleaningWriter.sln.  
  
2. Откройте окно командной строки и перейдите к каталогу, в котором сформирован файл ViewStageCleaningWriter.exe.  
  
3. Запустите ViewStateCleaningWriter.exe применительно к файлу Workflow1.xaml.  

   Синтаксис для этого исполняемого файла показан в следующем примере.  
  
   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```
   
   Это вывод файла XAML \[выходной_файл], который имеет все свои сведения о состоянии представления удалены.  
  
> [!NOTE]
> Что касается рабочего процесса <xref:System.Activities.Statements.Sequence>, то удаляется целый ряд подсказок виртуализации. Это вынуждает конструктор повторно вычислять макет при его следующей загрузке. При использовании этого образца для <xref:System.Activities.Statements.Flowchart> удаляется вся информация о расположении и маршрутизации линий, а при последующей загрузке в конструктор все действия отображаются в левой стороне экрана с наложением друг на друга.  
  
#### <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a>Создание образца файл XAML для использования с этим образцом  
  
1. Откройте [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2. Создайте новое консольное приложение рабочего процесса.  
  
3. Перетащите на полотно несколько действий  
  
4. Сохраните файл XAML рабочего процесса.  
  
5. Изучите файл XAML, чтобы видеть свойства, закрепленные за состоянием представления.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`
