---
title: Параметры типа нельзя использовать в качестве квалификаторов
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 974d2935e64151109b688f576229fb008b59b229
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819805"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Параметры типа нельзя использовать в качестве квалификаторов
Программный элемент квалифицируется с помощью уточняющей строке, которая включает параметр типа.  
  
 Параметр типа представляет требования для типа, который предоставляется при создании универсального типа. Он не представляет конкретный определенный тип. Строка квалификации должна включать только те элементы, которые определены во время компиляции.  
  
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
  
1.  Удалите параметр типа из уточняющей строке или замените его определенного типа.  
  
2.  Если вам нужно использовать для поиска элемента программирования имен сконструированный тип, необходимо использовать дополнительную логику программы.  
  
## <a name="see-also"></a>См. также

- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Список типов](../../../visual-basic/language-reference/statements/type-list.md)
