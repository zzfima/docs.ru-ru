---
title: Параметры типа нельзя использовать в качестве квалификаторов
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 563010efc4f3049d330ee2b38b7f59e23292e630
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Параметры типа нельзя использовать в качестве квалификаторов
Программный элемент квалифицировался уточняющей строки, которая содержит параметр типа.  
  
 Представляет параметр типа является обязательным для типа, которое должно быть предоставлено при создании универсального типа. Он не представляет конкретный определенный тип. Уточняющей строки должна включать только те элементы, которые определены во время компиляции.  
  
 Следующие операторы могут привести к этой ошибке.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **Идентификатор ошибки:** BC32098  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Удалите параметр типа из строки квалификации или замените его определенным типом.  
  
2.  Если необходимо использовать для поиска элемента программирования имен сконструированный тип, необходимо использовать дополнительную логику программы.  
  
## <a name="see-also"></a>См. также  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Универсальные типы в Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
