---
title: Создание вариативных универсальных интерфейсов
ms.date: 07/20/2015
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
ms.openlocfilehash: 74362b9d9effab028bebb9e9ecf72ac0111366d3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347070"
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a>Создание вариативных универсальных интерфейсов (Visual Basic)

Параметры универсального типа можно объявить в интерфейсах как ковариантные или контравариантные. *Ковариация* позволяет методам интерфейса иметь тип возвращаемого значения, степень наследования которого больше, чем указано в параметрах универсального типа. *Контравариантность* позволяет методам интерфейса иметь типы аргументов, степень наследования которых меньше, чем указано в параметре универсального типа. Универсальный интерфейс, который имеет ковариантные или контравариантные параметры универсального типа, называется *вариантным*.

> [!NOTE]
> В платформе .NET Framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов. Список вариативных интерфейсов в .NET Framework см. в разделе [вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).

## <a name="declaring-variant-generic-interfaces"></a>Объявление вариантных универсальных интерфейсов

Вариантные универсальные интерфейсы можно объявить с помощью ключевых слов `in` и `out` для параметров универсального типа.

> [!IMPORTANT]
> Параметры `ByRef` в Visual Basic не могут быть вариантными. Типы значений также не поддерживают вариативность.

Для объявления ковариантного параметра универсального типа можно использовать ключевое слово `out`. Ковариантный тип должен удовлетворять следующим условиям:

- Тип используется только в качестве типа значения, возвращаемого методами интерфейса, и не используется в качестве типа аргументов метода. Это показано в следующем примере, в котором тип `R` объявлен ковариантным.

    ```vb
    Interface ICovariant(Of Out R)
        Function GetSomething() As R
        ' The following statement generates a compiler error.
        ' Sub SetSomething(ByVal sampleArg As R)
    End Interface
    ```

    Существует одно исключение из данного правила. Если в качестве параметра метода используется контравариантный универсальный делегат, этот тип можно использовать в качестве параметра универсального типа для этого делегата. Это продемонстрировано ниже на примере типа `R`. Дополнительные сведения см. [в разделе вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [Использование вариативности для универсальных делегатов Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

    ```vb
    Interface ICovariant(Of Out R)
        Sub DoSomething(ByVal callback As Action(Of R))
    End Interface
    ```

- Тип не используется в качестве универсального ограничения для методов интерфейса. Это демонстрируется в следующем примере кода.

    ```vb
    Interface ICovariant(Of Out R)
        ' The following statement generates a compiler error
        ' because you can use only contravariant or invariant types
        ' in generic constraints.
        ' Sub DoSomething(Of T As R)()
    End Interface
    ```

Для объявления контравариантного параметра универсального типа можно использовать ключевое слово `in`. Контравариантный тип можно использовать только в качестве типа аргументов метода, но не в качестве типа значения, возвращаемого методами интерфейса. Контравариантный тип можно также использовать для универсальных ограничений. В следующем примере кода показано объявление контравариантного интерфейса и использование универсального ограничения для одного из его методов.

```vb
Interface IContravariant(Of In A)
    Sub SetSomething(ByVal sampleArg As A)
    Sub DoSomething(Of T As A)()
    ' The following statement generates a compiler error.
    ' Function GetSomething() As A
End Interface
```

Кроме того, можно реализовать поддержку ковариации и контравариации в одном интерфейсе, но для разных параметров типа, как показано в следующем примере кода.

```vb
Interface IVariant(Of Out R, In A)
    Function GetSomething() As R
    Sub SetSomething(ByVal sampleArg As A)
    Function GetSetSomething(ByVal sampleArg As A) As R
End Interface
```

В Visual Basic нельзя объявлять события в вариативных интерфейсах без указания типа делегата. Кроме того, вариантный интерфейс не может иметь вложенные классы, перечисления или структуры, но может иметь вложенные интерфейсы. Это демонстрируется в следующем примере кода.

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

## <a name="implementing-variant-generic-interfaces"></a>Реализация вариантных универсальных интерфейсов

Для реализации вариантных универсальных интерфейсов в классах используется тот же синтаксис, что и для инвариантных интерфейсов. В следующем примере кода показана реализация ковариантного интерфейса в универсальном классе.

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

Классы, которые реализуют вариантные интерфейсы, являются инвариантными. Например, рассмотрим следующий код.

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

## <a name="extending-variant-generic-interfaces"></a>Расширение вариантных универсальных интерфейсов

При расширении вариантных универсальных интерфейсов необходимо использовать ключевые слова `in` и `out` для явного указания того, поддерживает ли вариативность производный интерфейс. Компилятор не подразумевает вариативность интерфейса, который расширяется. Например, рассмотрим следующие интерфейсы.

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

В интерфейсе `Invariant(Of T)` параметр универсального типа `T` является инвариантным, в то время как в `IExtCovariant (Of Out T)`параметр типа является ковариантным, хотя оба интерфейса расширяют один и тот же интерфейс. То же правило применяется к контравариантным параметрам универсального типа.

Можно создать интерфейс, который расширяет и интерфейс, в котором параметр универсального типа `T` является ковариантным, и интерфейс, где он является контравариантным, если в расширяемом интерфейсе параметр универсального типа `T` является инвариантным. Это показано в следующем примере кода.

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IContravariant(Of In T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T), IContravariant(Of T)
End Interface
```

Тем не менее, если параметр универсального типа `T` объявлен ковариантным в одном интерфейсе, его нельзя объявить контравариантным в расширенном интерфейсе и наоборот. Это показано в следующем примере кода.

```vb
Interface ICovariant(Of Out T)
End Interface

' The following statements generate a compiler error.
' Interface ICoContraVariant(Of In T)
'     Inherits ICovariant(Of T)
' End Interface
```

### <a name="avoiding-ambiguity"></a>Недопущение неоднозначности

При реализации вариантных универсальных интерфейсов вариативность может приводить к неоднозначности. Этого следует избегать.

Например, если вы явно реализуете один вариантный универсальный интерфейс с разными параметрами универсального типа в одном классе, это может создавать неоднозначность. Компилятор не сообщает об ошибке в данном случае, но и не указывает, какая реализация интерфейса будет выбрана во время выполнения. Это может привести к возникновению неявных ошибок в коде. Рассмотрим следующий пример кода:

> [!NOTE]
> При использовании `Option Strict Off`Visual Basic создает предупреждение компилятора при возникновении неоднозначной реализации интерфейса. При использовании `Option Strict On`Visual Basic выдает ошибку компилятора.

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

В этом примере не указано, каким образом метод `pets.GetEnumerator` делает выбор между `Cat` и `Dog`. Это может вызвать проблемы в вашем коде.

## <a name="see-also"></a>См. также

- [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [Использование вариативности в универсальных методах-делегатах Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
