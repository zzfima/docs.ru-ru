---
title: Практическое руководство. Ссылка на текущий экземпляр объекта
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 62b22a54904a45380052d3d81d9415517d4f8d3b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346885"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a>Практическое руководство. Ссылка на текущий экземпляр объекта (Visual Basic)
*Текущим экземпляром* объекта является экземпляр, в котором в данный момент выполняется код.  
  
 Для ссылки на текущий экземпляр используется ключевое слово `Me`.  
  
### <a name="to-refer-to-the-current-instance"></a>Ссылка на текущий экземпляр  
  
- Используйте ключевое слово `Me`, в котором обычно используется имя объектной переменной.  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     Хотя `Me` ведет себя как объектная переменная, вы не можете объявить ее или присвоить ей что-либо. `Me` всегда ссылается на текущий экземпляр.  
  
## <a name="see-also"></a>См. также

- [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
