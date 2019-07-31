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
# <a name="serialize-workflows-and-activities-to-and-from-xaml"></a>Сериализация рабочих процессов и действий в XAML и из него

Кроме компиляции в содержащиеся в сборках типы определения рабочих процессов также могут быть сериализованы в XAML. Такие сериализованные определения могут быть загружены повторно для редактирования или просмотра, переданы в систему сборки для компиляции или загружены и вызваны. В этом разделе представлены общие сведения о сериализации определений рабочих процессов и работе с определениями рабочих процессов языка XAML.

## <a name="work-with-xaml-workflow-definitions"></a>Работа с определениями рабочих процессов XAML

Для создания определения рабочего процесса для сериализации используется класс <xref:System.Activities.ActivityBuilder>. Создание класса <xref:System.Activities.ActivityBuilder> очень похоже на создание <xref:System.Activities.DynamicActivity>. Можно указать любые необходимые аргументы и настроить действия, составляющие поведение. В следующем примере создается действие `Add`, которое принимает два входных аргумента, складывает их и возвращает результат. Поскольку это действие возвращает результат, используется универсальный класс <xref:System.Activities.ActivityBuilder%601>.

[!code-csharp[CFX_WorkflowApplicationExample#41](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]

Каждый экземпляр <xref:System.Activities.DynamicActivityProperty> представляет собой один входной аргумент для рабочего процесса, а класс <xref:System.Activities.ActivityBuilder.Implementation%2A> содержит действия, которые образуют логику рабочего процесса. Обратите внимание, что выражения правостороннего значения в этом примере - это выражения Visual Basic. Лямбда-выражения не могут быть сериализованы в языке XAML, если не используется <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>. Если сериализованные рабочие процессы должны открываться или редактироваться в конструкторе рабочих процессов, следует использовать Visual Basic выражения. Дополнительные сведения см. в разделе [создание рабочих процессов, действий и выражений с помощью императивного кода](authoring-workflows-activities-and-expressions-using-imperative-code.md).

Для сериализации определения рабочего процесса, представленного экземпляром <xref:System.Activities.ActivityBuilder> в языке XAML, используйте класс <xref:System.Activities.XamlIntegration.ActivityXamlServices>, чтобы создать <xref:System.Xaml.XamlWriter>, и затем класс <xref:System.Xaml.XamlServices>, чтобы сериализовать определение рабочего процесса с помощью <xref:System.Xaml.XamlWriter>. <xref:System.Activities.XamlIntegration.ActivityXamlServices>содержит методы для преобразования <xref:System.Activities.ActivityBuilder> экземпляров в XAML и обратно, а также для загрузки рабочих процессов XAML <xref:System.Activities.DynamicActivity> и возврата метода, который может быть вызван. В следующем примере <xref:System.Activities.ActivityBuilder> экземпляр из предыдущего примера сериализуется в строку и сохраняется в файл.

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

В следующем примере представлен сериализованный рабочий процесс.

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

Чтобы загрузить сериализованный рабочий процесс, используйте <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> метод. При этом сериализуется определение рабочего процесса и возвращается действие <xref:System.Activities.DynamicActivity>, представляющее определение рабочего процесса. Обратите внимание, что XAML не десериализуется до тех пор, пока действие <xref:System.Activities.Activity.CacheMetadata%2A> не будет вызвано для тела <xref:System.Activities.DynamicActivity> во время процесса проверки. Если проверка не вызывается явно, то она выполняется при вызове рабочего процесса. Если определение рабочего процесса XAML является недействительным, возникает исключение <xref:System.ArgumentException>. Исключения, возникающие из-за <xref:System.Activities.Activity.CacheMetadata%2A>, не реагируют на вызов <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> и должны быть обработаны вызывающим классом. В следующем примере сериализованный рабочий процесс из предыдущего примера загружается и вызывается с помощью класса <xref:System.Activities.WorkflowInvoker>.

[!code-csharp[CFX_WorkflowApplicationExample#43](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]

При вызове этого рабочего процесса на консоль выводятся следующие данные.

**25 + 15**\
**40**

> [!NOTE]
> Дополнительные сведения о вызове рабочих процессов с входными и выходными аргументами см. в разделе <xref:System.Activities.WorkflowInvoker.Invoke%2A> [использование WorkflowInvoker и WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) и.

Если сериализованный рабочий процесс содержит C# выражения, <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> экземпляр со <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> свойством, для `true` которого задано значение, должен передаваться <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>в качестве параметра <xref:System.NotSupportedException> в, в противном случае — будет создано с сообщением, аналогичным. следующим образом: **Для запуска типа действия выражения "Кшарпвалуе" 1 "требуется компиляция.  Убедитесь, что рабочий процесс скомпилирован.**

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

Дополнительные сведения см. в разделе [ C# выражения](csharp-expressions.md).

Сериализованное определение рабочего процесса также может быть загружено в <xref:System.Activities.ActivityBuilder> экземпляр с <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> помощью метода. После загрузки сериализованного рабочего процесса в <xref:System.Activities.ActivityBuilder> экземпляр его можно проверить и изменить. Это может быть полезно разработчикам пользовательских конструкторов рабочих процессов, а также реализует механизм сохранения и повторной загрузки определений рабочих процессов во время конструирования. В следующем примере загружается определение сериализованного рабочего процесса из предыдущего примера, после чего выполняется просмотр его свойств.

[!code-csharp[CFX_WorkflowApplicationExample#44](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
