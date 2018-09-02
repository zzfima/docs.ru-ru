---
title: Настраиваемое действие для переключения в диапазоне значений
ms.date: 03/30/2017
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
ms.openlocfilehash: cfaf4318b1557a9fc217de8254e164243ea54569
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417981"
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a>Настраиваемое действие для переключения в диапазоне значений
В этом образце демонстрируется создание настраиваемого действия, которое расширяет использование <xref:System.Activities.Statements.Switch%601>. Обычная инструкция <xref:System.Activities.Statements.Switch%601> позволяет выполнять переключение на основании одного значения. Но существуют бизнес-сценарии, в которых действие должно переключаться в зависимости от диапазона значений. Например, действие может выполнять одну операцию, если значение, по которому производится переключение, находится в диапазоне от 1 до 5, и другую операцию, если значение находится в диапазоне от 6 до 10, а также операцию по умолчанию для всех прочих значений. Это настраиваемое действие выполняет именно такую задачу.  
  
## <a name="the-switchrange-activity"></a>Действие SwitchRange  
 Действие `SwitchRange` планирует дочернее действие, если значение результата его выражения входит в диапазон одного из его `Cases`.  
  
 В следующем примере кода показано настраиваемое действие, которое переключается в зависимости от диапазона значений.  
  
```csharp  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|Свойство|Описание|  
|-|-|  
|Выражение|Здесь представлено выражение, которое вычисляется и сравнивается с диапазонами в списке вариантов. Результат выражения имеет тип T.|  
|Cases|Каждый вариант состоит из диапазона (From - от и To - до) и операции (Body - тело). Выражение вычисляется и сравнивается с диапазоном значений. Если результат выражения входит в диапазон одного из вариантов, выполняется соответствующее действие.|  
|По умолчанию|Действие, выполняемое в случае, если значение не соответствует ни одному варианту. При установке значения `null` не выполняется ни одно действие.|  
  
## <a name="caserange-class"></a>Класс CaseRange  
 Класс `CaseRange` представляет диапазон для действия в `SwitchRange`. Каждый экземпляр класса `CaseRange` содержит диапазон (включающий границы `From` и `To`) и элемент `Body` действия, которое планируется для выполнения, если вычисленное выражение в классе `SwitchRange` попадает в диапазон.  
  
 Следующий пример кода является определением для класса `CaseRange`.  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  И класс `SwitchRange`, и класс `CaseRange`, определенные в образце, являются универсальными классами, которые могут работать с любым типом, реализующим интерфейс `IComparable` аналогично классу <xref:System.Activities.Statements.Switch%601>.  
  
## <a name="sample-usage"></a>Использование примера  
 В следующем примере кода показано, как использовать действие `SwitchRange`.  
  
```csharp  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  С помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] откройте файл решения SwitchRange.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`