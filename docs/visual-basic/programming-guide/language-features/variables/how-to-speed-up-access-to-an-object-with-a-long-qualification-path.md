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
ms.openlocfilehash: d52d13feb0f85065c0623b5937f558b841c036dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-speed-up-access-to-an-object-with-a-long-qualification-path-visual-basic"></a>Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic)
При частом обращении к объект, который требуется указать путь квалификации несколько методов и свойств, можно ускорить код, не повторяя классификационный путь.  
  
 Повторение классификационного пути можно избежать двумя способами. Объект может быть присвоен переменной, или можно использовать его в `With`... `End With` блок.  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-assigning-it-to-a-variable"></a>Для ускорения доступа к объекту сильно полное путем присвоения переменной  
  
1.  Объявите переменную типа объекта, к которому часто осуществляется доступ. Укажите классификационный путь в части инициализации объявления.  
  
    ```  
    Dim ctrlActv As Control = someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Используйте переменную для доступа к членам объекта.  
  
    ```  
    ctrlActv.Text = "Test"  
    ctrlActv.Location = New Point(100, 100)  
    ctrlActv.Show()  
    ```  
  
### <a name="to-speed-up-access-to-a-heavily-qualified-object-by-using-a-withend-with-block"></a>Для ускорения доступа к сильно уточненное с помощью With... End With-блок  
  
1.  Поместите классификационный пусть `With` инструкции.  
  
    ```  
    With someForm.ActiveForm.ActiveControl  
    ```  
  
2.  Доступ к членам объекта внутри `With` блокировать перед `End With` инструкции.  
  
    ```  
        .Text = "Test"  
        .Location = New Point(100, 100)  
        .Show()  
    End With  
    ```  
  
## <a name="see-also"></a>См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Оператор With...End With](../../../../visual-basic/language-reference/statements/with-end-with-statement.md)
