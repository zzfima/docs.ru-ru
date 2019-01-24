---
title: Объектные переменные в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], about object variables
- variables [Visual Basic], object
- objects [Visual Basic], accessing
- object variables [Visual Basic]
ms.assetid: 6169a196-2b13-4ba5-a205-154bc1b87844
ms.openlocfilehash: 046119664fc0277a6a5305d0cf086b4438b13f9d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685468"
---
# <a name="object-variables-in-visual-basic"></a>Объектные переменные в Visual Basic
В дополнение к хранить значения, переменные могут ссылаться на объект. Объект присваивается переменной по тем же причинам, которые можно присвоить любое значение переменной:  
  
-   Имя переменной часто короче и легче для запоминания, чем полный путь к методы и свойства, необходимые для доступа к самому объекту.  
  
-   Использование переменной, которая ссылается на объект является более эффективным, чем несколько раз доступ к самому объекту через необходимые методы или свойства.  
  
-   Можно изменить переменную для ссылки на другие объекты во время выполнения кода.  
  
## <a name="making-code-shorter"></a>Уменьшение размера кода  
 Объектные переменные можно использовать для сокращения кода необходимо вводить. В следующем примере используется полный путь к методы и свойства для доступа к <xref:System.Windows.Forms.Control> объекта.  
  
```  
' Assume Me is a valid Form, or replace Me with a valid Form.  
Me.ActiveForm.ActiveControl.Text = "Test"  
Me.ActiveForm.ActiveControl.Location = New Point(100, 100)  
Me.ActiveForm.ActiveControl.Show()  
```  
  
 Можно сократить этот код и ускорить его выполнение при использовании переменной объекта для элемента управления. Следует объявить переменную объекта с определенный класс, который планируется назначить для него (`Control` в данном случае). После того как объект переменной, с ней можно работать точно так же, как обрабатывать объект, к которому он относится. Можно задать или получить свойства объекта или использовать любой из его методов. В следующем примере переменной объекта используется для упрощения кода в предыдущем примере.  
  
```  
Dim ctrlActv As System.Windows.Forms.Control = Me.ActiveForm.ActiveControl  
ctrlActv.Text = "Test"  
ctrlActv.Location = New Point(100, 100)  
ctrlActv.Show()  
```  
  
## <a name="see-also"></a>См. также
- [Объявление переменных](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Практическое руководство. Увеличение скорости доступа к объекту с длинным классификационным путем](../../../../visual-basic/programming-guide/language-features/variables/how-to-speed-up-access-to-an-object-with-a-long-qualification-path.md)
- [Объявление объектной переменной](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
