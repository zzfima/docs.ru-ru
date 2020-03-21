---
title: Выражения - WF
ms.date: 03/30/2017
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
ms.openlocfilehash: 93fe449e8fa6c50f715d842c2ef6a9ecbd31aff2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182929"
---
# <a name="expressions"></a>Выражения

Выражение Фонда рабочего процесса Windows (WF) — это любое действие, которое возвращает результат. Все действия выражений косвенно наследуются от класса <xref:System.Activities.Activity%601>, который содержит свойство <xref:System.Activities.OutArgument> с именем <xref:System.Activities.Activity%601.Result%2A> в качестве значения, возвращаемого действием. [!INCLUDE[wf1](../../../includes/wf1-md.md)] поставляется с множеством действий выражений от таких простых, как <xref:System.Activities.Expressions.VariableValue%601> и <xref:System.Activities.Expressions.VariableReference%601>, для доступа к одной переменной рабочего процесса с помощью действий оператора до таких сложных, как <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> и <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601>, которые обеспечивают доступ ко всем возможностям языка Visual Basic для получения результата. Дополнительные действия выражения можно создать путем наследования от <xref:System.Activities.CodeActivity%601> или <xref:System.Activities.NativeActivity%601>.

## <a name="using-expressions"></a>Использование выражений
 Конструктор рабочих процессов использует <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> и <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> для всех выражений в проектах Visual Basic <xref:Microsoft.CSharp.Activities.CSharpValue%601> и <xref:Microsoft.CSharp.Activities.CSharpReference%601> для выражений C# в проектах рабочих процессов.

> [!NOTE]
> Поддержка выражений C-выражения в проектах рабочего процесса была введена в .NET Framework 4.5. Для получения дополнительной [информации](csharp-expressions.md)см.

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

 При определении рабочего процесса в коде можно использовать любое действие выражения. Следующий пример показывает использование состава действий оператора для добавления трех цифр:

```csharp
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

 Тот же рабочий процесс может быть выражен более компактно с помощью выражений Лямбда, как показано в следующем примере:
  
```csharp
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

## <a name="extending-available-expressions-with-custom-expression-activities"></a>Расширение доступных выражений с помощью настраиваемых действий выражения

 Выражения в [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] можно расширить, что позволит создавать дополнительные действия выражения. В следующем примере показано действие, которое возвращает сумму трех целочисленных значений.

```csharp
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

 С помощью этого нового действия можно переписать предыдущий рабочий процесс, который добавил три значения, как показано в следующем примере:

```csharp
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

 Для получения дополнительной информации об [использовании](authoring-workflows-activities-and-expressions-using-imperative-code.md)выражений в коде см.
