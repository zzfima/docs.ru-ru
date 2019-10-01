---
title: Выражение рекурсивно вызывает содержащее свойство <propertyname>
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: 42177f22e632e4a05b1f0b4d934f3e56ab9ff0f2
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698565"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>Выражение рекурсивно вызывает содержащееся свойство "\<propertyname >"
Инструкция в процедуре `Set` определения свойства хранит значение в имени свойства.  
  
 Рекомендуемый подход к удержанию значения свойства — определить переменную `Private` в контейнере свойства и использовать ее в процедурах `Get` и `Set`. Процедура `Set` сохраняет входящее значение в этой переменной `Private`.  
  
 Процедура `Get` ведет себя как процедура `Function`, поэтому ей можно присвоить значение имени свойства и вернуть управление, выполнив инструкцию `End Get`. Однако рекомендуемый подход состоит в том, чтобы включить переменную `Private` в качестве значения в [операторе return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Процедура `Set` ведет себя как процедура `Sub`, которая не возвращает значение. Поэтому имя процедуры или свойства не имеет особого смысла в процедуре `Set`, и в ней нельзя хранить значение.  
  
 В следующем примере показан подход, который может вызвать эту ошибку, за которым следует рекомендуемый подход.  
  
```vb  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений и обработке предупреждений как ошибок см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42026  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Перепишите определение свойства, чтобы использовать рекомендуемый подход, как показано в предыдущем примере.  
  
## <a name="see-also"></a>См. также

- [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
