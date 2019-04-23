---
title: Ожидается инициализатор
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 0795fdc1c4b177e13979d7555cd7588217b8cb4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334969"
---
# <a name="initializer-expected"></a>Ожидается инициализатор
Предпринята попытка объявить экземпляр класса с помощью инициализатора объектов, в котором список инициализации пуст, как показано в следующем примере.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 По крайней мере одно поле или свойство должны быть инициализированы в списке инициализаторов, как показано в следующем примере.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Идентификатор ошибки:** BC30996  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Инициализация по крайней мере одно поле или свойство в инициализаторе или не использовать инициализатор объекта.  
  
## <a name="see-also"></a>См. также

- [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
