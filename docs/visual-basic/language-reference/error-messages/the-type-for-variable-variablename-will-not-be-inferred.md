---
title: Тип для переменной &#39; &lt;variablename&gt; &#39; не будет определен, так как она привязана к полю во включающей области
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: cb423e8dcced6956eb86d484607915030c91412b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>Тип для переменной &#39; &lt;variablename&gt; &#39; не будет определен, так как она привязана к полю во включающей области
Тип для переменной "\<variablename >" не будет определен, так как она привязана к полю во включающей области. Измените имя "\<variablename >", или используйте полное доменное имя (например, «Me.variablename» или «MyBase.variablename»).  
  
 Управляющая переменная цикла в коде имеет то же имя в поле класса или других внешней области видимости. Так как переменная управления используется без `As` предложения, он привязан к полю во включающей области, и компилятор не создает новую переменную и не вывести его тип.  
  
 В следующем примере `Index`, управляющая переменная в `For` инструкции, привязанный к `Index` в `Customer` класса. Компилятор не создает новую переменную для управляющей переменной `Index` или вывести его тип.  
  
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
  
 По умолчанию данное сообщение является предупреждением. Сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки см. в разделе [Настройка предупреждений в Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42110  
  
### <a name="to-address-this-warning"></a>Устранение предупреждения  
  
-   Сделайте управляющей переменной цикла локальной, изменив ее имя на идентификатор, который не является также именем поля класса.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   Уточняется, что переменная управления циклом привязывает со значением поля класса с помощью префикса `Me.` к имени переменной.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   Вместо того чтобы полагаться на вывод локального типа, воспользуйтесь `As` предложений, чтобы указать тип для переменной цикла.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>Пример  
 Ниже приведен предыдущий пример исправленный первым на месте.  
  
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
 [Оператор Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [Оператор For Each...Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Практическое руководство. Ссылка на текущий экземпляр объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
