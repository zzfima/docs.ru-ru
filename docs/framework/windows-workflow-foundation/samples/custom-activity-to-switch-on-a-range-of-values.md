---
title: "Настраиваемое действие для переключения в диапазоне значений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Настраиваемое действие для переключения в диапазоне значений
В этом образце демонстрируется создание настраиваемого действия, которое расширяет использование <xref:System.Activities.Statements.Switch%601>.Обычная инструкция <xref:System.Activities.Statements.Switch%601> позволяет выполнять переключение на основании одного значения.Но существуют бизнес\-сценарии, в которых действие должно переключаться в зависимости от диапазона значений.Например, действие может выполнять одну операцию, если значение, по которому производится переключение, находится в диапазоне от 1 до 5, и другую операцию, если значение находится в диапазоне от 6 до 10, а также операцию по умолчанию для всех прочих значений.Это настраиваемое действие выполняет именно такую задачу.  
  
## Действие SwitchRange  
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
  
|||  
|-|-|  
|Свойство|Описание|  
|Выражение|Здесь представлено выражение, которое вычисляется и сравнивается с диапазонами в списке вариантов.Результат выражения имеет тип T.|  
|Cases|Каждый вариант состоит из диапазона \(From — от и To — до\) и операции \(Body — тело\).Выражение вычисляется и сравнивается с диапазоном значений.Если результат выражения входит в диапазон одного из вариантов, выполняется соответствующее действие.|  
|Default|Действие, выполняемое в случае, если значение не соответствует ни одному варианту.При установке значения `null` не выполняется ни одно действие.|  
  
## Класс CaseRange  
 Класс `CaseRange` представляет диапазон для действия в `SwitchRange`.Каждый экземпляр класса `CaseRange` содержит диапазон \(включающий границы `From` и `To`\) и элемент `Body` действия, которое планируется для выполнения, если вычисленное выражение в классе `SwitchRange` попадает в диапазон.  
  
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
  
## Использование образца  
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
  
#### Использование этого образца  
  
1.  С помощью [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] откройте файл решения SwitchRange.sln.  
  
2.  Для построения решения нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`  
  
## См. также