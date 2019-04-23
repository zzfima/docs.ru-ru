---
title: Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
ms.openlocfilehash: 94c838a69aab9fcae9dc0c79b6038ee90e2369e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299141"
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic)
Если вы обращаетесь чаще всего объекта, который требует классификационным путем несколько методов и свойств, можно ускорить код, не повторяя путь квалификации.  
  
 Существует два способа, можно избежать повторение классификационного пути. Объект может быть присвоен переменной, или можно использовать его в `With`... `End With` блок.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Чтобы ускорить доступ к сильно уточненный объект, присвоив его переменной  
  
1. Объявите переменную типа объекта, который вы обращаетесь к часто. Укажите путь квалификации в части инициализации объявления.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2. Используйте переменную для доступа к членам объекта.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Чтобы ускорить доступ к сильно уточненный объект с помощью аргумента With... Блок End With  
  
1. Поместить путь квалификации в `With` инструкции.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2. Доступ к членам объекта внутри `With` блокируется, прежде чем `End With` инструкции.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>См. также

- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
