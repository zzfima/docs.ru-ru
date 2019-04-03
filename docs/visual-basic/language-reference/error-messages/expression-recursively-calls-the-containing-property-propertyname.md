---
title: Выражение рекурсивно вызывает содержащее свойство <propertyname>
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: a758d05cca5ca71943b0ef08184aef5b2c457739
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836848"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>Выражение рекурсивно вызывает содержащее его свойство "\<имя_свойства >"
Оператор в `Set` процедуры определения свойства сохраняет значение в имени свойства.  
  
 Рекомендуемый подход для хранения значений свойства является определение `Private` переменных в контейнере свойства и его использования в языках `Get` и `Set` процедуры. `Set` Процедура затем будет хранить входящее значение в этом `Private` переменной.  
  
 `Get` Процедура действует как `Function` процедуры, поэтому можно присвоить значение имени свойства и вернуть управление путем добавления `End Get` инструкции. Тем не менее рекомендуется включать `Private` переменной в качестве значения [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Set` Процедура действует как `Sub` процедуры, которая не возвращает значение. Таким образом, имя процедуры или свойства не имеет специального значения в пределах `Set` процедура и в ней нельзя хранить значение.  
  
 В следующем примере показано подход, который может вызывать эту ошибку, следуют рекомендуемый подход.  
  
```  
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
  
-   Перепишите определение свойства использовать рекомендуемый подход, как показано в предыдущем примере.  
  
## <a name="see-also"></a>См. также

- [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)
- [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
