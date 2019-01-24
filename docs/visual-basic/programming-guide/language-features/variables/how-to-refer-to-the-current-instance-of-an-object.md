---
title: Как выполнить Ссылка на текущий экземпляр объекта (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: d166ce62a2bb0522d1ca7011aeff7afe076c2d8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54542201"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Как выполнить Ссылка на текущий экземпляр объекта (Visual Basic)
*Текущего экземпляра* объекта является экземпляром, в котором в данный момент выполняется код.  
  
 Использовании `Me` ключевое слово для ссылки на текущий экземпляр.  
  
### <a name="to-refer-to-the-current-instance"></a>Для ссылки на текущий экземпляр  
  
-   Использовать `Me` ключевое слово, где обычно лучше использовать имя переменной объекта.  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Несмотря на то что `Me` ведет себя как объект переменной, нельзя объявить ее или назначать ничего ее. `Me` всегда ссылается на текущий экземпляр.  
  
## <a name="see-also"></a>См. также
- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
