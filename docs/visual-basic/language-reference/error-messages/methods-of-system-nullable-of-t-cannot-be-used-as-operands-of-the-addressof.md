---
title: Методы System.Nullable(Of T) нельзя использовать в качестве операндов оператора AddressOf
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 54d66a60d20a6add4c2b4a160f87b58b5a1d00e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58817270"
---
# <a name="methods-of-systemnullableof-t-cannot-be-used-as-operands-of-the-addressof-operator"></a>Методы System.Nullable(Of T) нельзя использовать в качестве операндов оператора AddressOf
В операторе используется `AddressOf` с операндом, представляющим процедуру <xref:System.Nullable%601> структуры.  
  
 **Идентификатор ошибки:** BC32126  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Замените имя процедуры в `AddressOf` предложение с операндом, который не является членом <xref:System.Nullable%601>.  
  
-   Напишите класс-оболочку для метода <xref:System.Nullable%601> , вы хотите использовать. В следующем примере `NullableWrapper` класс определяет новый метод с именем `GetValueOrDefault`. Так как этот новый метод не является членом <xref:System.Nullable%601>, он может быть применен к `nullInstance`, экземпляр обнуляемого типа, для формирования аргумента для `AddressOf`.  
  
```vb  
Module Module1  
  
    Delegate Function Deleg() As Integer  
  
    Sub Main()  
        Dim nullInstance As New Nullable(Of Integer)(1)  
  
        Dim del As Deleg  
  
        ' GetValueOrDefault is a method of the Nullable generic  
        ' type. It cannot be used as an operand of AddressOf.  
        ' del = AddressOf nullInstance.GetValueOrDefault  
  
        ' The following line uses the GetValueOrDefault method  
        ' defined in the NullableWrapper class.  
        del = AddressOf (New NullableWrapper(  
            Of Integer)(nullInstance)).GetValueOrDefault  
  
        Console.WriteLine(del.Invoke())  
    End Sub  
  
    Class NullableWrapper(Of T As Structure)  
        Private m_Value As Nullable(Of T)  
  
        Sub New(ByVal Value As Nullable(Of T))  
            m_Value = Value  
        End Sub  
  
        Public Function GetValueOrDefault() As T  
            Return m_Value.Value  
        End Function  
    End Class  
End Module  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Nullable%601>
- [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
