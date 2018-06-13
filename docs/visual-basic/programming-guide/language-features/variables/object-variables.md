---
title: Объектные переменные в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 8383261c1806732c4c8abea9834000f003a848a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649117"
---
# <a name="object-variables-in-visual-basic"></a>Объектные переменные в Visual Basic
Помимо хранить значения, переменные могут ссылаться на объект. Объект присваивается переменной по тем же причинам, которые можно присвоить любое значение переменной:  
  
-   Имя переменной является часто короче и проще запомнить, чем полный путь методов и свойств, необходимых для доступа к самому объекту.  
  
-   С помощью переменной, которая ссылается на объект является более эффективным, чем повторяющееся обращение к самому объекту через необходимые методы или свойства.  
  
-   Можно изменить переменную для ссылки на другие объекты во время выполнения приложения.  
  
## <a name="making-code-shorter"></a>Уменьшение размера кода  
 Объектные переменные можно использовать для сокращения вводимого кода. В следующем примере используется полное методы и свойства для доступа к <xref:System.Windows.Forms.Control> объекта.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Можно сократить этот код и ускорения выполнения, если объектная переменная используется для элемента управления. Следует объявить переменную объекта в определенном классе, который требуется присвоить его (`Control` в данном случае). После того как объект переменной, с ней можно работать точно так же, как с объектом, к которому он относится. Можно задать или получить свойства объекта или использовать любой из его методов. В следующем примере переменной объекта для упрощения кода в предыдущем примере.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>См. также  
 [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)  
 [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
