---
title: Методы &#39;System.Nullable (Of T)&#39; нельзя использовать в качестве операндов &#39;AddressOf&#39; оператор
ms.date: 07/20/2015
f1_keywords:
- vbc32126
- bc32126
helpviewer_keywords:
- BC32126
ms.assetid: 2325668b-e2ad-40ee-a1ec-30450236c20d
ms.openlocfilehash: 3a3e4fc033f47fb6a72076dff79f1eece8d01a30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594124"
---
# <a name="methods-of-39systemnullableof-t39-cannot-be-used-as-operands-of-the-39addressof39-operator"></a>Методы &#39;System.Nullable (Of T)&#39; нельзя использовать в качестве операндов &#39;AddressOf&#39; оператор
Инструкция использует `AddressOf` с операндом, представляющим процедуру <xref:System.Nullable%601> структуры.  
  
 **Идентификатор ошибки:** BC32126  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Замените имя процедуры в `AddressOf` предложение with операнд, который не является членом <xref:System.Nullable%601>.  
  
-   Напишите класс-оболочку для метода <xref:System.Nullable%601> , которую требуется использовать. В следующем примере `NullableWrapper` класс определяет новый метод с именем `GetValueOrDefault`. Так как это новый метод не является членом <xref:System.Nullable%601>, он может быть применен к `nullInstance`, экземпляра типа nullable, для формирования аргумента для `AddressOf`.  
  
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
 <xref:System.Nullable%601>  
 [Оператор AddressOf](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
