---
title: Тип для переменной <variablename> не будет определен, так как она привязана к полю во включающей области
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: e56529919945558df178e18a83a895a79bfe4919
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512725"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a>Тип для переменной "\<variablename >" не будет определен, так как он привязан к полю во внешней области видимости

Тип для переменной "\<variablename >" не будет определен, так как он привязан к полю во внешней области видимости. Либо измените имя "\<variablename >", либо используйте полное имя (например, "Me. variablename" или "MyBase. variablename").

Переменная цикла в коде имеет то же имя, что и поле класса или другой включающей области. Так как переменная управления используется без `As` предложения, она привязывается к полю во включающей области, и компилятор не создает для него новую переменную или не выводит ее тип.

В следующем примере `Index`переменная элемента управления `For` в операторе привязана `Customer` к `Index` полю в классе. Компилятор не создает новую переменную для управляющей переменной `Index` или выводит ее тип.

```vb
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

- Сделайте переменную управления циклом локальной, изменив ее имя на идентификатор, который не является именем поля класса.

  ```vb
  For I = 1 To 10
  ```

- Уточните, что управляющая переменная цикла привязывается к полю класса путем `Me.` добавления префикса к имени переменной.

  ```vb
  For Me.Index = 1 To 10
  ```

- Вместо того чтобы полагаться на вывод локального типа, используйте `As` предложение, чтобы указать тип для управляющей переменной цикла.

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a>Пример
 В следующем коде показан предыдущий пример с первым исправлением.

```vb
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
