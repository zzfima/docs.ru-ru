---
title: "Тип переменной &quot;&lt;variablename&gt;&quot; не будет определен, так как она привязана к полю во включающей области | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42110
- bc42110
dev_langs:
- VB
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: 33
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ab7d69c34a58dc898553868258c4fdf6b81db343
ms.lasthandoff: 03/13/2017

---
# <a name="the-type-for-variable-39ltvariablenamegt39-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>Тип переменной "&lt;variablename&gt;" не будет определен, так как она привязана к полю во включающей области
Тип переменной "\<variablename настроек" не будет определен, так как она привязана к полю во включающей области. Либо измените имя "\<variablename настроек", или использовать полное доменное имя (например, «Me.variablename» или «MyBase.variablename»).  
  
 Переменная управления циклом в коде имеет то же имя, как поле класса или других внешней области видимости. Поскольку управляющая переменная используется без `As` предложения, он привязан к полю во включающей области, и компилятор не создает новую переменную и не вывести его тип.  
  
 В следующем примере `Index`, управляющая переменная в `For` инструкции, привязан к `Index` в `Customer` класса. Компилятор не создает новую переменную для переменной `Index` или вывести его тип.  
  
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
  
 По умолчанию данное сообщение является предупреждением. Сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки в разделе [в Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Идентификатор ошибки:** BC42110  
  
### <a name="to-address-this-warning"></a>Устранение предупреждения  
  
-   Сделайте локальной переменной цикла, изменив ее имя на идентификатор, который не является также именем поля класса.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   Уточняется, что переменная управления циклом привязывается к полю класса с помощью префикса `Me.` на имя переменной.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   Вместо того чтобы использовать вывод локального типа, используйте `As` предложение, чтобы указать тип для переменной цикла.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## <a name="example"></a>Пример  
 В следующем коде показано ранее примере с первого исправления на месте.  
  
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
 [Для каждого... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Для... Следующий оператор](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Практическое руководство: ссылки на текущий экземпляр объекта](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Me, My, MyBase и MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
