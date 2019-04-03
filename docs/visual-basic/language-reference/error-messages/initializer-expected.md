---
title: Ожидается инициализатор
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 77cfeb57bc313ded2d2c4d5a0c59041c5c19f515
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826084"
---
# <a name="initializer-expected"></a>Ожидается инициализатор
Предпринята попытка объявить экземпляр класса с помощью инициализатора объектов, в котором список инициализации пуст, как показано в следующем примере.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 По крайней мере одно поле или свойство должны быть инициализированы в списке инициализаторов, как показано в следующем примере.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Идентификатор ошибки:** BC30996  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Инициализация по крайней мере одно поле или свойство в инициализаторе или не использовать инициализатор объекта.  
  
## <a name="see-also"></a>См. также

- [Инициализаторы объектов. Именованные и анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Практическое руководство. Объявление объекта с помощью инициализатора объектов](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
