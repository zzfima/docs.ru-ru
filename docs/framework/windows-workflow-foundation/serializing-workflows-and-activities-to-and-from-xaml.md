---
title: "Сериализация рабочих процессов и действий в XAML и обратно"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c1954f02aef13599f7bd24f8e2d136f0f876256
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="serializing-workflows-and-activities-to-and-from-xaml"></a>Сериализация рабочих процессов и действий в XAML и обратно
Кроме компиляции в содержащиеся в сборках типы определения рабочих процессов также могут быть сериализованы в XAML. Такие сериализованные определения могут быть загружены повторно для редактирования или просмотра, переданы в систему сборки для компиляции или загружены и вызваны. В этом разделе представлены общие сведения о сериализации определений рабочих процессов и работе с определениями рабочих процессов языка XAML.  
  
## <a name="working-with-xaml-workflow-definitions"></a>Работа с определениями рабочих процессов XAML  
 Для создания определения рабочего процесса для сериализации используется класс <xref:System.Activities.ActivityBuilder>. Создание класса <xref:System.Activities.ActivityBuilder> очень похоже на создание <xref:System.Activities.DynamicActivity>. Можно указать любые необходимые аргументы и настроить действия, составляющие поведение. В следующем примере создается действие `Add`, которое принимает два входных аргумента, складывает их и возвращает результат. Поскольку это действие возвращает результат, используется универсальный класс <xref:System.Activities.ActivityBuilder%601>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 Каждый экземпляр <xref:System.Activities.DynamicActivityProperty> представляет собой один входной аргумент для рабочего процесса, а класс <xref:System.Activities.ActivityBuilder.Implementation%2A> содержит действия, которые образуют логику рабочего процесса. Обратите внимание, что выражения правостороннего значения в этом примере - это выражения Visual Basic. Лямбда-выражения не могут быть сериализованы в языке XAML, если не используется <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>. Если сериализованные рабочие процессы будут открыты или отредактированы в конструкторе рабочих процессов, то следует использовать выражения Visual Basic. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Разработки рабочих процессов, действий и выражений с помощью императивного кода](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
 Для сериализации определения рабочего процесса, представленного экземпляром <xref:System.Activities.ActivityBuilder> в языке XAML, используйте класс <xref:System.Activities.XamlIntegration.ActivityXamlServices>, чтобы создать <xref:System.Xaml.XamlWriter>, и затем класс <xref:System.Xaml.XamlServices>, чтобы сериализовать определение рабочего процесса с помощью <xref:System.Xaml.XamlWriter>. <xref:System.Activities.XamlIntegration.ActivityXamlServices> содержит методы для сопоставления экземпляров <xref:System.Activities.ActivityBuilder> с языка XAML и обратно, а также для загрузки рабочих процессов XAML и получения <xref:System.Activities.DynamicActivity>, которое впоследствии можно вызвать. В следующем примере экземпляр <xref:System.Activities.ActivityBuilder> из предыдущего примера сериализуется в строку, а также сохраняется в файл.  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
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
  
 Для загрузки сериализованного рабочего процесса, <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> используется метод. При этом сериализуется определение рабочего процесса и возвращается действие <xref:System.Activities.DynamicActivity>, представляющее определение рабочего процесса. Обратите внимание, что XAML не десериализуется до тех пор, пока действие <xref:System.Activities.Activity.CacheMetadata%2A> не будет вызвано для тела <xref:System.Activities.DynamicActivity> во время процесса проверки. Если проверка не вызывается явным образом, то она выполняется при вызове рабочего процесса. Если определение рабочего процесса XAML является недействительным, возникает исключение <xref:System.Argument>. Исключения, возникающие из-за <xref:System.Activities.Activity.CacheMetadata%2A>, не реагируют на вызов <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> и должны быть обработаны вызывающим классом. В следующем примере сериализованный рабочий процесс из предыдущего примера загружается и вызывается с помощью класса <xref:System.Activities.WorkflowInvoker>.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 При вызове этого рабочего процесса на консоль выводятся следующие данные.  
  
 **25 + 15**  
**40**    
> [!NOTE]
>  [!INCLUDE[crabout](../../../includes/crabout-md.md)]вызов рабочих процессов с входные и выходные аргументы, в разделе [использование WorkflowInvoker и WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) и <xref:System.Activities.WorkflowInvoker.Invoke%2A>.  
  
 Если сериализованный рабочий процесс содержит выражения C#, то <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> экземпляра с его <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> свойство `true` должен быть передан в качестве параметра <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, в противном случае <xref:System.NotSupportedException> будет создано сообщение, похожее на следующие: `Expression Activity type 'CSharpValue`1" должны быть скомпилированы для запуска.  Убедитесь, что рабочий процесс был скомпилирован. "  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Выражения C#](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).  
  
 Определение сериализованного рабочего процесса, также могут быть загружены в <xref:System.Activities.ActivityBuilder> экземпляра с помощью <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> метод. После загрузки сериализованного рабочего процесса в экземпляр <xref:System.Activities.ActivityBuilder> процесс можно просматривать и изменять. Это может быть полезно разработчикам пользовательских конструкторов рабочих процессов, а также реализует механизм сохранения и повторной загрузки определений рабочих процессов во время конструирования. В следующем примере загружается определение сериализованного рабочего процесса из предыдущего примера, после чего выполняется просмотр его свойств.  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
