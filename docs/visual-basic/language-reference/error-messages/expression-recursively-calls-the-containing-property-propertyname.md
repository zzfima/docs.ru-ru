---
title: Выражение рекурсивно вызывает содержащееся свойство &#39; &lt;propertyname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: f14e2645772b22a8f6ff2385dcd316a42d1d5cf0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588847"
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a>Выражение рекурсивно вызывает содержащееся свойство &#39; &lt;propertyname&gt;&#39;
Оператор в `Set` процедура определения свойства сохраняет значение в имени свойства.  
  
 Рекомендуемый подход для хранения значения свойства является определение `Private` переменных в контейнере свойства и использование его в `Get` и `Set` процедуры. `Set` Процедура затем будет хранить входящее значение в этом `Private` переменной.  
  
 `Get` Процедура действует как `Function` процедуру, чтобы он мог присвоить значение имени свойства и вернуть управление путем добавления `End Get` инструкции. Рекомендуемый подход, то, чтобы включить `Private` переменной в качестве значения при [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 `Set` Процедура действует как `Sub` процедуры, которая не возвращает значение. Таким образом, имя процедуры или свойства не имеет особого смысла в `Set` процедура и в ней нельзя хранить значение.  
  
 В следующем примере демонстрируется подход, который может вызвать эту ошибку, следуют рекомендуемый подход.  
  
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
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о скрытии предупреждений или обработке предупреждений как ошибок см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42026  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Перепишите определение свойства для использования рекомендуемый подход, как показано в предыдущем примере.  
  
## <a name="see-also"></a>См. также  
 [Процедуры свойств](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Оператор Property](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Оператор Set](../../../visual-basic/language-reference/statements/set-statement.md)
