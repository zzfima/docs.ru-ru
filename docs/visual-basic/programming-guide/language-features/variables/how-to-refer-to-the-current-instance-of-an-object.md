---
title: Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: c1b79f1b6a9768941d6fe966c5b5886ea742f808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)
*Текущего экземпляра* объекта является экземпляром, в котором в данный момент выполняется код.  
  
 Вы используете `Me` ключевое слово для ссылки на текущий экземпляр.  
  
### <a name="to-refer-to-the-current-instance"></a>Для ссылки на текущий экземпляр  
  
-   Использовать `Me` ключевое слово, где обычно лучше использовать имя переменной объекта.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Несмотря на то что `Me` ведет себя подобно объектной переменной, нельзя объявить его или ее присвоить ничего. `Me` всегда ссылается на текущий экземпляр.  
  
## <a name="see-also"></a>См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
