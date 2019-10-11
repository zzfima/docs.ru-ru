---
title: Параметры типа нельзя использовать в качестве квалификаторов
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 3ff4b189539bf119351a94dabadd596c336ac723
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250327"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Параметры типа нельзя использовать в качестве квалификаторов

Элемент программирования дополняется уточняющей строкой, включающей параметр типа.

Параметр типа представляет требование для типа, который должен предоставляться при создании универсального типа. Он не представляет определенный определенный тип. Уточняющая строка должна включать только те элементы, которые определены во время компиляции.

Следующий код может вызвать эту ошибку:

```vb  
Public Function CheckText(Of c As System.Windows.Forms.Control)(
    badText As String) As Boolean
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.
End Function  
```  
  
 **Идентификатор ошибки:** BC32098  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Удалите параметр типа из строки квалификации или замените его определенным типом.  
  
2. Если необходимо использовать сконструированный тип для нахождение квалифицированного программного элемента, необходимо использовать дополнительную логику программы.  
  
## <a name="see-also"></a>См. также

- [Ссылки на объявленные элементы](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Generic Types in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Список типов](../statements/type-list.md)
