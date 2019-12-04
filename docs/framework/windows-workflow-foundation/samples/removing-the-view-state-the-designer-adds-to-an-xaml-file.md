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
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="32e5d-102">Удаление состояния представления, добавляемого конструктором в файл XAML</span><span class="sxs-lookup"><span data-stu-id="32e5d-102">Removing the view state the designer adds to an XAML file</span></span>

<span data-ttu-id="32e5d-103">Этот образец демонстрирует создание класса, производного от <xref:System.Xaml.XamlWriter>, и удаление состояния представления из файла XAML.</span><span class="sxs-lookup"><span data-stu-id="32e5d-103">This sample demonstrates how to create a class that derives from <xref:System.Xaml.XamlWriter> and removes view state from a XAML file.</span></span> <span data-ttu-id="32e5d-104">Конструктор рабочих процессов Windows записывает сведения в документ XAML, который называется состоянием представления.</span><span class="sxs-lookup"><span data-stu-id="32e5d-104">Windows Workflow Designer writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="32e5d-105">Состоянием представления называются сведения, которые требуются во время разработки, такие как расположение макета, и не требуются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="32e5d-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> <span data-ttu-id="32e5d-106">Конструктор рабочих процессов вставляет эти сведения в документ XAML при редактировании.</span><span class="sxs-lookup"><span data-stu-id="32e5d-106">Workflow Designer inserts this information into the XAML document as it is edited.</span></span> <span data-ttu-id="32e5d-107">Конструктор рабочих процессов записывает состояние представления в XAML-файл с атрибутом `mc:Ignorable`, поэтому эти сведения не загружаются, когда среда выполнения загружает XAML-файл.</span><span class="sxs-lookup"><span data-stu-id="32e5d-107">Workflow Designer writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="32e5d-108">Этот образец демонстрирует, как создать класс, который удаляет указанные сведения о состоянии представления при обработке узлов XAML.</span><span class="sxs-lookup"><span data-stu-id="32e5d-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>

## <a name="discussion"></a><span data-ttu-id="32e5d-109">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="32e5d-109">Discussion</span></span>

<span data-ttu-id="32e5d-110">Этот образец демонстрирует создание пользовательского модуля записи.</span><span class="sxs-lookup"><span data-stu-id="32e5d-110">This sample demonstrates how to create a custom writer.</span></span>

<span data-ttu-id="32e5d-111">Чтобы сформировать пользовательский модуль записи XAML, создайте класс, который наследует от <xref:System.Xaml.XamlWriter>.</span><span class="sxs-lookup"><span data-stu-id="32e5d-111">To build a custom XAML writer, create a class that inherits from <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="32e5d-112">Так как средства записи XAML часто являются вложенными, обычно отслеживается внутренний модуль записи XAML.</span><span class="sxs-lookup"><span data-stu-id="32e5d-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="32e5d-113">Эти "внутренние" модули записи можно рассматривать как ссылку на оставшийся стек средств записи XAML, что позволяет иметь несколько точек входа для выполнения работы, а затем делегировать обработку в оставшуюся часть стека.</span><span class="sxs-lookup"><span data-stu-id="32e5d-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>

<span data-ttu-id="32e5d-114">В этом образце есть несколько особенностей, представляющих интерес.</span><span class="sxs-lookup"><span data-stu-id="32e5d-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="32e5d-115">Одна из них состоит в том, что проводится проверка для определения принадлежности записываемого элемента пространству имен конструктора.</span><span class="sxs-lookup"><span data-stu-id="32e5d-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="32e5d-116">Обратите внимание на то, что при этом исключается также использование других типов из пространства имен конструктора в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="32e5d-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>

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

<span data-ttu-id="32e5d-117">Кроме того, при этом создается стек элементов XAML, которые используются при прохождении потока узла.</span><span class="sxs-lookup"><span data-stu-id="32e5d-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="32e5d-118">Остальная часть работы в этом образце в основном выполняется в методе `WriteStartMember`.</span><span class="sxs-lookup"><span data-stu-id="32e5d-118">The remaining work of this sample is largely contained in the `WriteStartMember` method.</span></span>

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

<span data-ttu-id="32e5d-119">Затем последующие методы проверяют, содержатся ли до сих пор в контейнере состояния представления, и в случае положительного ответа выполняют возврат, а не передают узел в направлении к нижней части стека модулей записи.</span><span class="sxs-lookup"><span data-stu-id="32e5d-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>

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

<span data-ttu-id="32e5d-120">Чтобы использовать пользовательский модуль записи XAML, необходимо соединить его вместе с другими в стеке модулей записи XAML.</span><span class="sxs-lookup"><span data-stu-id="32e5d-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="32e5d-121">В следующем коде показано, как это можно использовать.</span><span class="sxs-lookup"><span data-stu-id="32e5d-121">The following code shows how this can be used.</span></span>

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

## <a name="to-use-this-sample"></a><span data-ttu-id="32e5d-122">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="32e5d-122">To use this sample</span></span>

1. <span data-ttu-id="32e5d-123">С помощью Visual Studio 2010 откройте файл решения Виевстатеклеанингвритер. sln.</span><span class="sxs-lookup"><span data-stu-id="32e5d-123">Using Visual Studio 2010, open the ViewStateCleaningWriter.sln solution file.</span></span>

2. <span data-ttu-id="32e5d-124">Откройте окно командной строки и перейдите к каталогу, в котором сформирован файл ViewStageCleaningWriter.exe.</span><span class="sxs-lookup"><span data-stu-id="32e5d-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>

3. <span data-ttu-id="32e5d-125">Запустите ViewStateCleaningWriter.exe применительно к файлу Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="32e5d-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>

   <span data-ttu-id="32e5d-126">Синтаксис для этого исполняемого файла показан в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="32e5d-126">The syntax for the executable is shown in the following example.</span></span>

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   <span data-ttu-id="32e5d-127">Это выводит XAML-файл для \[файла], в котором все сведения о состоянии представления удалены.</span><span class="sxs-lookup"><span data-stu-id="32e5d-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>

> [!NOTE]
> <span data-ttu-id="32e5d-128">Что касается рабочего процесса <xref:System.Activities.Statements.Sequence>, то удаляется целый ряд подсказок виртуализации.</span><span class="sxs-lookup"><span data-stu-id="32e5d-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="32e5d-129">Это вынуждает конструктор повторно вычислять макет при его следующей загрузке.</span><span class="sxs-lookup"><span data-stu-id="32e5d-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="32e5d-130">При использовании этого образца для <xref:System.Activities.Statements.Flowchart> удаляется вся информация о расположении и маршрутизации линий, а при последующей загрузке в конструктор все действия отображаются в левой стороне экрана с наложением друг на друга.</span><span class="sxs-lookup"><span data-stu-id="32e5d-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="32e5d-131">Создание образца файл XAML для использования с этим образцом</span><span class="sxs-lookup"><span data-stu-id="32e5d-131">To create a sample XAML file for use with this sample</span></span>

1. <span data-ttu-id="32e5d-132">Откройте Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="32e5d-132">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="32e5d-133">Создайте новое консольное приложение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="32e5d-133">Create a new Workflow Console Application.</span></span>

3. <span data-ttu-id="32e5d-134">Перетащите на полотно несколько действий</span><span class="sxs-lookup"><span data-stu-id="32e5d-134">Drag and drop a few activities onto the canvas</span></span>

4. <span data-ttu-id="32e5d-135">Сохраните файл XAML рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="32e5d-135">Save the workflow XAML file.</span></span>

5. <span data-ttu-id="32e5d-136">Изучите файл XAML, чтобы видеть свойства, закрепленные за состоянием представления.</span><span class="sxs-lookup"><span data-stu-id="32e5d-136">Inspect the XAML file to see the view state attached properties.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32e5d-137">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="32e5d-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="32e5d-138">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="32e5d-138">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="32e5d-139">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="32e5d-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="32e5d-140">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="32e5d-140">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`
