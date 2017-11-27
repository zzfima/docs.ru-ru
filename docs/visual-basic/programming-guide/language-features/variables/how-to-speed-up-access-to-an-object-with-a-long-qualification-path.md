---
title: "Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], accessing
- variables [Visual Basic], object
- With statement [Visual Basic]
- With block
- object variables [Visual Basic], accessing
ms.assetid: 3eb7657f-c9fe-4e05-8bc3-4bb14d5ae585
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d91eeaeb034a4c8b4fefcffdf2fdebe72127d66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
