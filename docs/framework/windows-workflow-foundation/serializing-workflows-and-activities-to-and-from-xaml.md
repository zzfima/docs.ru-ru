---
title: Сериализация рабочих процессов и действий в XAML и обратно
ms.date: 03/30/2017
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
ms.openlocfilehash: c18afa7232adabc4f1c4e17fde993064b9189e39
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671898"
---
# <a name="serialize-workflows-and-activities-to-and-from-xaml"></a><span data-ttu-id="660ec-102">Сериализация рабочих процессов и действий в XAML и из него</span><span class="sxs-lookup"><span data-stu-id="660ec-102">Serialize Workflows and Activities to and from XAML</span></span>

<span data-ttu-id="660ec-103">Кроме компиляции в содержащиеся в сборках типы определения рабочих процессов также могут быть сериализованы в XAML.</span><span class="sxs-lookup"><span data-stu-id="660ec-103">In addition to being compiled into types that are contained in assemblies, workflow definitions can also be serialized to XAML.</span></span> <span data-ttu-id="660ec-104">Такие сериализованные определения могут быть загружены повторно для редактирования или просмотра, переданы в систему сборки для компиляции или загружены и вызваны.</span><span class="sxs-lookup"><span data-stu-id="660ec-104">These serialized definitions can be reloaded for editing or inspection, passed to a build system for compilation, or loaded and invoked.</span></span> <span data-ttu-id="660ec-105">В этом разделе представлены общие сведения о сериализации определений рабочих процессов и работе с определениями рабочих процессов языка XAML.</span><span class="sxs-lookup"><span data-stu-id="660ec-105">This topic provides an overview of serializing workflow definitions and working with XAML workflow definitions.</span></span>

## <a name="work-with-xaml-workflow-definitions"></a><span data-ttu-id="660ec-106">Работа с определениями рабочих процессов XAML</span><span class="sxs-lookup"><span data-stu-id="660ec-106">Work with XAML Workflow definitions</span></span>

<span data-ttu-id="660ec-107">Для создания определения рабочего процесса для сериализации используется класс <xref:System.Activities.ActivityBuilder>.</span><span class="sxs-lookup"><span data-stu-id="660ec-107">To create a workflow definition for serialization, the <xref:System.Activities.ActivityBuilder> class is used.</span></span> <span data-ttu-id="660ec-108">Создание класса <xref:System.Activities.ActivityBuilder> очень похоже на создание <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="660ec-108">Creating an <xref:System.Activities.ActivityBuilder> is very similar to creating a <xref:System.Activities.DynamicActivity>.</span></span> <span data-ttu-id="660ec-109">Можно указать любые необходимые аргументы и настроить действия, составляющие поведение.</span><span class="sxs-lookup"><span data-stu-id="660ec-109">Any desired arguments are specified, and the activities that constitute the behavior are configured.</span></span> <span data-ttu-id="660ec-110">В следующем примере создается действие `Add`, которое принимает два входных аргумента, складывает их и возвращает результат.</span><span class="sxs-lookup"><span data-stu-id="660ec-110">In the following example, an `Add` activity is created that takes two input arguments, adds them together, and returns the result.</span></span> <span data-ttu-id="660ec-111">Поскольку это действие возвращает результат, используется универсальный класс <xref:System.Activities.ActivityBuilder%601>.</span><span class="sxs-lookup"><span data-stu-id="660ec-111">Because this activity returns a result, the generic <xref:System.Activities.ActivityBuilder%601> class is used.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#41](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]

<span data-ttu-id="660ec-112">Каждый экземпляр <xref:System.Activities.DynamicActivityProperty> представляет собой один входной аргумент для рабочего процесса, а класс <xref:System.Activities.ActivityBuilder.Implementation%2A> содержит действия, которые образуют логику рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="660ec-112">Each of the <xref:System.Activities.DynamicActivityProperty> instances represents one of the input arguments to the workflow, and the <xref:System.Activities.ActivityBuilder.Implementation%2A> contains the activities that make up the logic of the workflow.</span></span> <span data-ttu-id="660ec-113">Обратите внимание, что выражения правостороннего значения в этом примере - это выражения Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="660ec-113">Note that the r-value expressions in this example are Visual Basic expressions.</span></span> <span data-ttu-id="660ec-114">Лямбда-выражения не могут быть сериализованы в языке XAML, если не используется <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>.</span><span class="sxs-lookup"><span data-stu-id="660ec-114">Lambda expressions are not serializable to XAML unless <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> is used.</span></span> <span data-ttu-id="660ec-115">Если сериализованные рабочие процессы должны открываться или редактироваться в конструкторе рабочих процессов, следует использовать Visual Basic выражения.</span><span class="sxs-lookup"><span data-stu-id="660ec-115">If the serialized workflows are intended to be opened or edited in the workflow designer, then Visual Basic expressions should be used.</span></span> <span data-ttu-id="660ec-116">Дополнительные сведения см. в разделе [создание рабочих процессов, действий и выражений с помощью императивного кода](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="660ec-116">For more information, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

<span data-ttu-id="660ec-117">Для сериализации определения рабочего процесса, представленного экземпляром <xref:System.Activities.ActivityBuilder> в языке XAML, используйте класс <xref:System.Activities.XamlIntegration.ActivityXamlServices>, чтобы создать <xref:System.Xaml.XamlWriter>, и затем класс <xref:System.Xaml.XamlServices>, чтобы сериализовать определение рабочего процесса с помощью <xref:System.Xaml.XamlWriter>.</span><span class="sxs-lookup"><span data-stu-id="660ec-117">To serialize the workflow definition represented by the <xref:System.Activities.ActivityBuilder> instance to XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> to create a <xref:System.Xaml.XamlWriter>, and then use <xref:System.Xaml.XamlServices> to serialize the workflow definition by using the <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="660ec-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices>содержит методы для преобразования <xref:System.Activities.ActivityBuilder> экземпляров в XAML и обратно, а также для загрузки рабочих процессов XAML <xref:System.Activities.DynamicActivity> и возврата метода, который может быть вызван.</span><span class="sxs-lookup"><span data-stu-id="660ec-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> has methods to map <xref:System.Activities.ActivityBuilder> instances to and from XAML and to load XAML workflows and return a <xref:System.Activities.DynamicActivity> that can be invoked.</span></span> <span data-ttu-id="660ec-119">В следующем примере <xref:System.Activities.ActivityBuilder> экземпляр из предыдущего примера сериализуется в строку и сохраняется в файл.</span><span class="sxs-lookup"><span data-stu-id="660ec-119">In the following example, the <xref:System.Activities.ActivityBuilder> instance from the previous example is serialized to a string and saved to a file.</span></span>

```csharp
// Serialize the workflow to XAML and store it in a string.
StringBuilder sb = new StringBuilder();
StringWriter tw = new StringWriter(sb);
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
string serializedAB = sb.ToString();

// Display the XAML to the console.
Console.WriteLine(serializedAB);

// Serialize the workflow to XAML and save it to a file.
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw2, ab);
sw.Close();
```

<span data-ttu-id="660ec-120">В следующем примере представлен сериализованный рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="660ec-120">The following example represents the serialized workflow.</span></span>

```xaml
<Activity
  x:TypeArguments="x:Int32"
  x:Class="Add"
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <x:Members>
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />
  </x:Members>
  <Sequence>
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">
      <Assign.To>
        <OutArgument x:TypeArguments="x:Int32">
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />
          </OutArgument>
      </Assign.To>
    </Assign>
  </Sequence>
</Activity>
```

<span data-ttu-id="660ec-121">Чтобы загрузить сериализованный рабочий процесс, используйте <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="660ec-121">To load a serialized workflow, use the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="660ec-122">При этом сериализуется определение рабочего процесса и возвращается действие <xref:System.Activities.DynamicActivity>, представляющее определение рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="660ec-122">This takes the serialized workflow definition and returns a <xref:System.Activities.DynamicActivity> that represents the workflow definition.</span></span> <span data-ttu-id="660ec-123">Обратите внимание, что XAML не десериализуется до тех пор, пока действие <xref:System.Activities.Activity.CacheMetadata%2A> не будет вызвано для тела <xref:System.Activities.DynamicActivity> во время процесса проверки.</span><span class="sxs-lookup"><span data-stu-id="660ec-123">Note that the XAML is not deserialized until <xref:System.Activities.Activity.CacheMetadata%2A> is called on the body of the <xref:System.Activities.DynamicActivity> during the validation process.</span></span> <span data-ttu-id="660ec-124">Если проверка не вызывается явно, то она выполняется при вызове рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="660ec-124">If validation is not explicitly called, then it is performed when the workflow is invoked.</span></span> <span data-ttu-id="660ec-125">Если определение рабочего процесса XAML является недействительным, возникает исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="660ec-125">If the XAML workflow definition is invalid, then an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="660ec-126">Исключения, возникающие из-за <xref:System.Activities.Activity.CacheMetadata%2A>, не реагируют на вызов <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> и должны быть обработаны вызывающим классом.</span><span class="sxs-lookup"><span data-stu-id="660ec-126">Any exceptions thrown from <xref:System.Activities.Activity.CacheMetadata%2A> escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span> <span data-ttu-id="660ec-127">В следующем примере сериализованный рабочий процесс из предыдущего примера загружается и вызывается с помощью класса <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="660ec-127">In the following example, the serialized workflow from the previous example is loaded and invoked by using <xref:System.Activities.WorkflowInvoker>.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#43](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]

<span data-ttu-id="660ec-128">При вызове этого рабочего процесса на консоль выводятся следующие данные.</span><span class="sxs-lookup"><span data-stu-id="660ec-128">When this workflow is invoked, the following output is displayed to the console.</span></span>

<span data-ttu-id="660ec-129">**25 + 15**</span><span class="sxs-lookup"><span data-stu-id="660ec-129">**25 + 15**</span></span>\
<span data-ttu-id="660ec-130">**40**</span><span class="sxs-lookup"><span data-stu-id="660ec-130">**40**</span></span>

> [!NOTE]
> <span data-ttu-id="660ec-131">Дополнительные сведения о вызове рабочих процессов с входными и выходными аргументами см. в разделе <xref:System.Activities.WorkflowInvoker.Invoke%2A> [использование WorkflowInvoker и WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) и.</span><span class="sxs-lookup"><span data-stu-id="660ec-131">For more information about invoking workflows with input and output arguments, see [Using WorkflowInvoker and WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) and <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span>

<span data-ttu-id="660ec-132">Если сериализованный рабочий процесс содержит C# выражения, <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> экземпляр со <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> свойством, для `true` которого задано значение, должен передаваться <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>в качестве параметра <xref:System.NotSupportedException> в, в противном случае — будет создано с сообщением, аналогичным. следующим образом: **Для запуска типа действия выражения "Кшарпвалуе" 1 "требуется компиляция.  Убедитесь, что рабочий процесс скомпилирован.**</span><span class="sxs-lookup"><span data-stu-id="660ec-132">If the serialized workflow contains C# expressions, then an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true` must be passed as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, otherwise a <xref:System.NotSupportedException> will be thrown with a message similar to the following: **Expression Activity type 'CSharpValue\`1' requires compilation in order to run.  Please ensure that the workflow has been compiled.**</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

<span data-ttu-id="660ec-133">Дополнительные сведения см. в разделе [ C# выражения](csharp-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="660ec-133">For more information, see [C# Expressions](csharp-expressions.md).</span></span>

<span data-ttu-id="660ec-134">Сериализованное определение рабочего процесса также может быть загружено в <xref:System.Activities.ActivityBuilder> экземпляр с <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> помощью метода.</span><span class="sxs-lookup"><span data-stu-id="660ec-134">A serialized workflow definition can also be loaded into an <xref:System.Activities.ActivityBuilder> instance by using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> method.</span></span> <span data-ttu-id="660ec-135">После загрузки сериализованного рабочего процесса в <xref:System.Activities.ActivityBuilder> экземпляр его можно проверить и изменить.</span><span class="sxs-lookup"><span data-stu-id="660ec-135">After a serialized workflow is loaded into an <xref:System.Activities.ActivityBuilder> instance, it can be inspected and modified.</span></span> <span data-ttu-id="660ec-136">Это может быть полезно разработчикам пользовательских конструкторов рабочих процессов, а также реализует механизм сохранения и повторной загрузки определений рабочих процессов во время конструирования.</span><span class="sxs-lookup"><span data-stu-id="660ec-136">This is useful for custom workflow designer authors and provides a mechanism for saving and reloading workflow definitions during the design process.</span></span> <span data-ttu-id="660ec-137">В следующем примере загружается определение сериализованного рабочего процесса из предыдущего примера, после чего выполняется просмотр его свойств.</span><span class="sxs-lookup"><span data-stu-id="660ec-137">In the following example, the serialized workflow definition from the previous example is loaded and its properties are inspected.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#44](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
