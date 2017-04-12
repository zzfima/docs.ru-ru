---
title: "Создание вариативных универсальных интерфейсов (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 324e2a906e84950aa9019bbf68a524458492646e
ms.lasthandoff: 03/13/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a>Создание вариативных универсальных интерфейсов (Visual Basic)
Можно объявить параметры универсального типа в интерфейсах как ковариантные или контравариантные. *Ковариация* позволяет методам интерфейса иметь более производные типы возвращаемых значений, чем указано параметрами универсального типа. *Контрвариантность* позволяет методам интерфейса иметь типы аргументов, для которых меньше, чем указано параметрами универсального. Универсальный интерфейс, который имеет ковариантные или контравариантные параметры универсального типа, называется *вариант*.  
  
> [!NOTE]
>  Платформа .NET framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов. Список вариативных интерфейсов в платформе .NET Framework см. в разделе [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  
  
## <a name="declaring-variant-generic-interfaces"></a>Объявление вариативных универсальных интерфейсов  
 Вариативные универсальные интерфейсы можно объявить с помощью `in` и `out` ключевые слова для параметров универсального типа.  
  
> [!IMPORTANT]
>  `ByRef`в Visual Basic не может быть типа variant. Типы значений также не поддерживают вариативность.  
  
 Параметр универсального типа можно объявить ковариантный с помощью `out` ключевое слово. Ковариантный тип должен удовлетворять следующим условиям:  
  
-   Тип используется только как тип возвращаемого значения методов интерфейса и не используется в качестве типа аргументов метода. Это показано в следующем примере, в котором тип `R` объявлен ковариантным.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     Существует одно исключение из данного правила. Если контравариантный универсальный делегат в качестве параметра метода, можно использовать тип параметра универсального типа для делегата. Это показано с помощью типа `R` в следующем примере. Дополнительные сведения см. в разделе [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [с помощью дисперсию Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   Тип не используется в качестве универсального ограничения для методов интерфейса. Это показано в следующем коде.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 Контравариантного параметра универсального типа можно объявить с помощью `in` ключевое слово. Контравариантный тип можно использовать только в качестве типа аргументов метода, а не как тип возвращаемого значения методов интерфейса. Контравариантный тип можно использовать также для универсальных ограничений. В следующем коде показано объявление контравариантного интерфейса и использование универсального ограничения для одного из его методов.  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 Это также можно реализовать поддержку ковариации и контравариации в тот же интерфейс, но для разных параметров типа, как показано в следующем примере кода.  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 В Visual Basic нельзя объявлять события в вариативных интерфейсах без указания типа делегата. Кроме того вариантный интерфейс не может включать вложенные классы, перечисления или структуры, но он может включать вложенные интерфейсы. Это показано в следующем коде.  
  
```vb  
Interface ICovariant(Of Out R)  
    ' The following statement generates a compiler error.  
    ' Event SampleEvent()  
    ' The following statement specifies the delegate type and   
    ' does not generate an error.  
    Event AnotherEvent As EventHandler  
  
    ' The following statements generate compiler errors,  
    ' because a variant interface cannot have  
    ' nested enums, classes, or structures.  
  
    'Enum SampleEnum : test : End Enum  
    'Class SampleClass : End Class  
    'Structure SampleStructure : Dim value As Integer : End Structure  
  
    ' Variant interfaces can have nested interfaces.  
    Interface INested : End Interface  
End Interface  
```  
  
## <a name="implementing-variant-generic-interfaces"></a>Реализация вариативных универсальных интерфейсов  
 Для реализации вариативных универсальных интерфейсов в классах, используя тот же синтаксис, используемый для инвариантных интерфейсов. В следующем примере кода показана реализация ковариантного интерфейса в универсальном классе.  
  
```vb  
Interface ICovariant(Of Out R)  
    Function GetSomething() As R  
End Interface  
  
Class SampleImplementation(Of R)  
    Implements ICovariant(Of R)  
    Public Function GetSomething() As R _  
    Implements ICovariant(Of R).GetSomething  
        ' Some code.  
    End Function  
End Class  
```  
  
 Классы, которые реализуют вариативные интерфейсы, являются инвариантными. Например, рассмотрим следующий код.  
  
```vb  
 The interface is covariant.  
Dim ibutton As ICovariant(Of Button) =  
    New SampleImplementation(Of Button)  
Dim iobj As ICovariant(Of Object) = ibutton  
  
' The class is invariant.  
Dim button As SampleImplementation(Of Button) =  
    New SampleImplementation(Of Button)  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim obj As SampleImplementation(Of Object) = button  
```  
  
## <a name="extending-variant-generic-interfaces"></a>Расширение вариативных универсальных интерфейсов  
 При расширении вариативных универсальных интерфейсов необходимо использовать `in` и `out` ключевые слова для явного указания того, поддерживает ли вариативность производный интерфейс. Компилятор не подразумевает вариативность интерфейса, который расширяется. Например рассмотрим следующие интерфейсы.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T)  
End Interface  
  
Interface IExtCovariant(Of Out T)  
    Inherits ICovariant(Of T)  
End Interface  
```  
  
 В `Invariant(Of T)` интерфейса параметра универсального типа `T` является инвариантным, тогда как в `IExtCovariant (Of Out T)`параметр типа является ковариантным, хотя оба интерфейса расширяют тот же интерфейс. То же правило применяется к контравариантные параметры универсального типа.  
  
 Можно создать интерфейс, который расширяет и интерфейс, в котором параметр универсального типа `T` является ковариантным, и интерфейс, где является контравариантным, если в расширяемом интерфейсе параметр универсального типа `T` является неизменяемым. Это показано в следующем примере кода.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 Тем не менее если параметр универсального типа `T` является объявлен ковариантным в одном интерфейсе, его нельзя объявить контравариантным в расширенном интерфейсе и наоборот. Это показано в следующем примере кода.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a>Чтобы избежать неоднозначности  
 При реализации вариативных универсальных интерфейсов вариативность может привести к неоднозначности. Этого следует избегать.  
  
 Например если же вариантных универсальных интерфейсов с разными обобщенными параметрами явно реализовать в один класс, можно создать неоднозначности. Компилятор сообщает об ошибке, в данном случае, но не указано, какая реализация интерфейса будет выбрана во время выполнения. Это может привести к возникновению неявных ошибок в коде. Рассмотрим следующий пример кода.  
  
> [!NOTE]
>  С `Option Strict Off`, Visual Basic создаст предупреждение компилятора при наличии неоднозначной реализации интерфейса. С `Option Strict On`, Visual Basic создает ошибку компилятора.  
  
```vb  
' Simple class hierarchy.  
Class Animal  
End Class  
  
Class Cat  
    Inherits Animal  
End Class  
  
Class Dog  
    Inherits Animal  
End Class  
  
' This class introduces ambiguity  
' because IEnumerable(Of Out T) is covariant.  
Class Pets  
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)  
  
    Public Function GetEnumerator() As IEnumerator(Of Cat) _  
        Implements IEnumerable(Of Cat).GetEnumerator  
        Console.WriteLine("Cat")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator(Of Dog) _  
        Implements IEnumerable(Of Dog).GetEnumerator  
        Console.WriteLine("Dog")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator2() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
        ' Some code.  
    End Function  
End Class  
  
Sub Main()  
    Dim pets As IEnumerable(Of Animal) = New Pets()  
    pets.GetEnumerator()  
End Sub  
```  
  
 В этом примере не указано как `pets.GetEnumerator` метод выбирает между `Cat` и `Dog`. Это может вызвать проблемы в коде.  
  
## <a name="see-also"></a>См. также  
 [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)   
 [Использование вариативности в Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
