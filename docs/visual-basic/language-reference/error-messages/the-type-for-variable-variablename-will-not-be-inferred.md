---
title: Тип для переменной <variablename> не будет определен, так как она привязана к полю во включающей области
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: bcd142785d8ee736c6a1b41950fae80e4d26fa18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013651"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>Тип для переменной "\<имя_переменной >" не будет определен, так как она привязана к полю во включающей области
Тип для переменной "\<имя_переменной >" не будет определен, так как она привязана к полю во включающей области. Либо измените имя "\<имя_переменной >", или используйте полное доменное имя (например, «Me.variablename» или «MyBase.variablename»).  
  
 Управляющая переменная цикла в коде имеет имя, как поле класса или других внешней области видимости. Так как переменная управления используется без `As` предложение, он привязан к полю во включающей области, и компилятор не создает новую переменную для него и вывести его тип.  
  
 В следующем примере `Index`, управляющая переменная в `For` инструкции, привязан к `Index` в `Customer` класса. Компилятор не создает новую переменную для управляющей переменной `Index` или вывести его тип.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
 По умолчанию данное сообщение является предупреждением. Дополнительные сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки, см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42110  
  
### <a name="to-address-this-warning"></a>Устранение предупреждения  
  
- Сделайте локальный управляющей переменной цикла, изменив его имя на идентификатор, который не совпадает с именем поля класса.  
  
    ```  
    For I = 1 To 10  
    ```  
  
- Уточняется, что управляющей переменной цикла привязывается к полю класса предваряя `Me.` к имени переменной.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
- Вместо того чтобы вывод локального типа, используйте `As` предложение, чтобы указать тип управляющей переменной цикла for.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>Пример  
 В следующем коде показано приведенного выше, в результате первого исправления на месте.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>См. также

- [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Практическое руководство. Ссылка на текущий экземпляр объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
