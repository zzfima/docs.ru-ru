---
title: "Предоставление данных с помощью CacheMetadata"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 34832f23-e93b-40e6-a80b-606a855a00d9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a25e658d512cf0575a4e3902a9a951099675e29a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="exposing-data-with-cachemetadata"></a>Предоставление данных с помощью CacheMetadata
Перед выполнением действия среда выполнения рабочих процессов получает все сведения, которые необходимы для его поддержки. Среда выполнения получает эти данные во время выполнения метода <xref:System.Activities.Activity.CacheMetadata%2A>. Реализация этого метода по умолчанию предоставляет среде выполнения все открытые аргументы, переменные и дочерние действия этого действия, доступные во время выполнения. Если действие требует передачи среде выполнения дополнительных сведений (например, закрытых элементов или действий, планируемых этим действием), то этот метод может быть переопределен.  
  
## <a name="default-cachemetadata-behavior"></a>Поведение CacheMetadata по умолчанию  
 Реализация <xref:System.Activities.NativeActivity.CacheMetadata%2A> по умолчанию для действий, производных от <xref:System.Activities.NativeActivity>, обрабатывает следующие типы методов следующими способами:  
  
-   <xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601> или <xref:System.Activities.InOutArgument%601> (универсальные аргументы). Эти аргументы доступны в среде выполнения с именем и типом, совпадающими с именем и типом переданного свойства, с соответствующим направлением аргумента и некоторыми проверочными данными.  
  
-   <xref:System.Activities.Variable> или любой его подкласс. Эти элементы предоставляются среде выполнения в виде открытых переменных.  
  
-   <xref:System.Activities.Activity> или любой его подкласс. Эти элементы предоставляются среде выполнения в виде открытых дочерних действий. Поведение по умолчанию может быть реализовано явным образом, вызовом <xref:System.Activities.ActivityMetadata.AddImportedChild%2A> с передачей дочернего действия.  
  
-   <xref:System.Activities.ActivityDelegate> или любой его подкласс. Эти элементы доступны в среде выполнения в виде открытых делегатов.  
  
-   <xref:System.Collections.ICollection> типа <xref:System.Activities.Variable>. Все элементы коллекции передаются среде выполнения в виде открытых переменных.  
  
-   <xref:System.Collections.ICollection> типа <xref:System.Activities.Activity>. Все элементы коллекции передаются среде выполнения в виде открытых дочерних действий.  
  
-   <xref:System.Collections.ICollection> типа <xref:System.Activities.ActivityDelegate>. Все элементы коллекции передаются среде выполнения в виде открытых делегатов.  
  
 <xref:System.Activities.Activity.CacheMetadata%2A> для действий, производных от <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity> и <xref:System.Activities.AsyncCodeActivity>, работают, как описано выше, за исключением следующих отличий.  
  
-   Классы, производные от <xref:System.Activities.Activity>, не могут планировать дочерние действия или делегаты, поэтому такие элементы предоставляются в виде импортируемых дочерних действий и делегатов.  
  
-   Классы, производные от <xref:System.Activities.CodeActivity> и <xref:System.Activities.AsyncCodeActivity>, не поддерживают переменные, дочерние элементы и делегаты, поэтому передаваться могут только аргументы.  
  
## <a name="overriding-cachemetadata-to-provide-information-to-the-runtime"></a>Переопределение метода CacheMetadata для передачи данных среде выполнения  
 В следующем фрагменте кода показано, как добавить сведения об элементах в метаданные любого действия во время выполнения метода <xref:System.Activities.Activity.CacheMetadata%2A>. Следует иметь в виду, что основа метода вызывается для кэширования всех открытых данных о действии.  
  
```  
protected override void CacheMetadata(NativeActivityMetadata metadata)  
{      
    base.CacheMetadata(metadata);  
    metadata.AddImplementationChild(this._writeLine);  
    metadata.AddVariable(this._myVariable);  
    metadata.AddImplementationVariable(this._myImplementationVariable);  
  
    RuntimeArgument argument = new RuntimeArgument("MyArgument", ArgumentDirection.In, typeof(SomeType));  
    metadata.Bind(argument, this.SomeName);  
    metadata.AddArgument(argument);  
}  
```  
  
## <a name="using-cachemetadata-to-expose-implementation-children"></a>Доступ к дочерним элементам реализации через метод CacheMetadata  
 Чтобы передать данные дочерним действиям, которые должны быть запланированы действием с помощью переменных, необходимо добавить переменные в виде переменных реализации. Значения открытых переменных нельзя задать таким образом. Причина этого заключается в том, что действия должны выполняться скорее как реализации функций (имеющих параметры), а не как инкапсулированные классы (имеющие свойства). Однако в некоторых ситуациях аргументы должны задаваться явным образом, например через <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, поскольку запланированное действие, в отличие от дочернего, не имеет доступа к аргументам родительского действия.  
  
 В следующем фрагменте кода показан способ передачи аргумента от исходного действия запланированному действию с помощью <xref:System.Activities.Activity.CacheMetadata%2A>.  
  
```  
public sealed class ChildActivity : NativeActivity  
{  
    public WriteLine _writeLine;  
    public InArgument<string> Message { get; set; }  
    private Variable<string> MessageVariable { get; set; }  
    public ChildActivity()  
    {  
        MessageVariable = new Variable<string>();  
        _writeLine = new WriteLine  
        {  
            Text = new InArgument<string>(MessageVariable),  
        };  
    }  
    protected override void CacheMetadata(NativeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        metadata.AddImplementationVariable(this.MessageVariable);  
        metadata.AddImplementationChild(this._writeLine);  
    }  
    protected override void Execute(NativeActivityContext context)  
    {  
        string configuredMessage = context.GetValue(Message);  
        context.SetValue(MessageVariable, configuredMessage);  
        context.ScheduleActivity(this._writeLine);  
    }  
}  
```
