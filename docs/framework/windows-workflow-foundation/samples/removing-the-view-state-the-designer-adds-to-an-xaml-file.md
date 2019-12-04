---
title: Удаление состояния представления, добавляемого конструктором в файл XAML, WF
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: f431275140e821aa5ec4d2235322f06be87d5ee2
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715612"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a>Удаление состояния представления, добавляемого конструктором в файл XAML

Этот образец демонстрирует создание класса, производного от <xref:System.Xaml.XamlWriter>, и удаление состояния представления из файла XAML. Конструктор рабочих процессов Windows записывает сведения в документ XAML, который называется состоянием представления. Состоянием представления называются сведения, которые требуются во время разработки, такие как расположение макета, и не требуются во время выполнения. Конструктор рабочих процессов вставляет эти сведения в документ XAML при редактировании. Конструктор рабочих процессов записывает состояние представления в XAML-файл с атрибутом `mc:Ignorable`, поэтому эти сведения не загружаются, когда среда выполнения загружает XAML-файл. Этот образец демонстрирует, как создать класс, который удаляет указанные сведения о состоянии представления при обработке узлов XAML.

## <a name="discussion"></a>Обсуждение

Этот образец демонстрирует создание пользовательского модуля записи.

Чтобы сформировать пользовательский модуль записи XAML, создайте класс, который наследует от <xref:System.Xaml.XamlWriter>. Так как средства записи XAML часто являются вложенными, обычно отслеживается внутренний модуль записи XAML. Эти "внутренние" модули записи можно рассматривать как ссылку на оставшийся стек средств записи XAML, что позволяет иметь несколько точек входа для выполнения работы, а затем делегировать обработку в оставшуюся часть стека.

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

Кроме того, при этом создается стек элементов XAML, которые используются при прохождении потока узла. Остальная часть работы в этом образце в основном выполняется в методе `WriteStartMember`.

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

## <a name="to-use-this-sample"></a>Использование этого образца

1. С помощью Visual Studio 2010 откройте файл решения Виевстатеклеанингвритер. sln.

2. Откройте окно командной строки и перейдите к каталогу, в котором сформирован файл ViewStageCleaningWriter.exe.

3. Запустите ViewStateCleaningWriter.exe применительно к файлу Workflow1.xaml.

   Синтаксис для этого исполняемого файла показан в следующем примере.

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   Это выводит XAML-файл для \[файла], в котором все сведения о состоянии представления удалены.

> [!NOTE]
> Что касается рабочего процесса <xref:System.Activities.Statements.Sequence>, то удаляется целый ряд подсказок виртуализации. Это вынуждает конструктор повторно вычислять макет при его следующей загрузке. При использовании этого образца для <xref:System.Activities.Statements.Flowchart> удаляется вся информация о расположении и маршрутизации линий, а при последующей загрузке в конструктор все действия отображаются в левой стороне экрана с наложением друг на друга.

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a>Создание образца файл XAML для использования с этим образцом

1. Откройте Visual Studio 2010.

2. Создайте новое консольное приложение рабочего процесса.

3. Перетащите на полотно несколько действий

4. Сохраните файл XAML рабочего процесса.

5. Изучите файл XAML, чтобы видеть свойства, закрепленные за состоянием представления.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`
