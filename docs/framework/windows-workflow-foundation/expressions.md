---
title: Expressions1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 805a49d45da308744fc528b63e8a74bb69bbd124
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="expressions"></a>Выражения
Выражение Windows Workflow Foundation (WF) — любое действие, которое возвращает результат. Все действия выражений косвенно наследуются от класса <xref:System.Activities.Activity%601>, который содержит свойство <xref:System.Activities.OutArgument> с именем <xref:System.Activities.Activity%601.Result%2A> в качестве значения, возвращаемого действием. [!INCLUDE[wf1](../../../includes/wf1-md.md)] поставляется с множеством действий выражений от таких простых, как <xref:System.Activities.Expressions.VariableValue%601> и <xref:System.Activities.Expressions.VariableReference%601>, для доступа к одной переменной рабочего процесса с помощью действий оператора до таких сложных, как <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> и <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>, которые обеспечивают доступ ко всем возможностям языка Visual Basic для получения результата. Дополнительные действия выражения можно создать путем наследования от <xref:System.Activities.CodeActivity%601> или <xref:System.Activities.NativeActivity%601>.  
  
## <a name="using-expressions"></a>Использование выражений  
 Конструктор рабочих процессов использует <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> и <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> для всех выражений в проектах Visual Basic <xref:Microsoft.CSharp.Activities.CSharpValue%601> и <xref:Microsoft.CSharp.Activities.CSharpReference%601> для выражений C# в проектах рабочих процессов.  
  
> [!NOTE]
>  Поддержка выражений C# в проектах рабочих процессов появилась в [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Дополнительные сведения см. в разделе [выражения C#](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).  
  
 Рабочие процессы, которые создаются конструктором, сохраняются в XAML, в котором выражения отображаются в квадратных скобках, как показано в следующем примере.  
  
```xml  
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <Sequence.Variables>  
    <Variable x:TypeArguments="x:Int32" Default="1" Name="a" />  
    <Variable x:TypeArguments="x:Int32" Default="2" Name="b" />  
    <Variable x:TypeArguments="x:Int32" Default="3" Name="c" />  
    <Variable x:TypeArguments="x:Int32" Default="0" Name="r" />  
  </Sequence.Variables>  
  <Assign>  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:Int32">[r]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:Int32">[a + b + c]</InArgument>  
    </Assign.Value>  
  </Assign>  
</Sequence>  
```  
  
 При определении рабочего процесса в коде можно использовать любое действие выражения. В следующем примере показано использование способа создания действий оператора для сложения трех чисел.  
  
```  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int> {  
                Expression = new Add<int, int, int> {  
                    Left = new Add<int, int, int> {  
                        Left = new InArgument<int>(a),  
                        Right = new InArgument<int>(b)  
                    },  
                    Right = new InArgument<int>(c)  
                }  
            }  
        }  
    }  
};  
```  
  
 Этот же рабочий процесс может быть выражен более компактно с помощью лямбда-выражений C#, как показано в следующем примере.  
  
```  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int>((ctx) => a.Get(ctx) + b.Get(ctx) + c.Get(ctx))  
        }  
    }  
};  
```  
  
 Также рабочий процесс можно выразить с помощью действий выражений Visual Basic, как показано в следующем примере.  
  
```  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int>(new VisualBasicValue<int>("a + b + c"))  
        }  
    }  
};  
```  
  
## <a name="extending-available-expressions-with-custom-expression-activities"></a>Расширение доступных выражений с помощью настраиваемых действий выражения  
 Выражения в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] можно расширить, что позволит создавать дополнительные действия выражения. В следующем примере показано действие, которое возвращает сумму трех целочисленных значений.  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Activities;  
  
namespace ExpressionsDemo  
{  
    public sealed class AddThreeValues : CodeActivity<int>  
    {  
        public InArgument<int> Value1 { get; set; }  
        public InArgument<int> Value2 { get; set; }  
        public InArgument<int> Value3 { get; set; }  
  
        protected override int Execute(CodeActivityContext context)  
        {  
            return Value1.Get(context) +   
                   Value2.Get(context) +   
                   Value3.Get(context);  
        }  
    }  
}  
```  
  
 С помощью этого нового действия можно переписать предыдущий рабочий процесс, в котором складывались три значения, как показано в следующем примере.  
  
```  
Variable<int> a = new Variable<int>("a", 1);  
Variable<int> b = new Variable<int>("b", 2);  
Variable<int> c = new Variable<int>("c", 3);  
Variable<int> r = new Variable<int>("r", 0);  
  
Sequence w = new Sequence  
{  
    Variables = { a, b, c, r },  
    Activities =   
    {  
        new Assign {  
            To = new OutArgument<int>(r),  
            Value = new InArgument<int> {  
                Expression = new AddThreeValues() {  
                    Value1 = new InArgument<int>(a),  
                    Value2 = new InArgument<int>(b),  
                    Value3 = new InArgument<int>(c)  
                }  
            }  
        }  
    }  
};  
```  
  
 Дополнительные сведения об использовании выражений в коде см. в разделе [разработки рабочих процессов, действий и выражений с помощью императивного кода](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).
