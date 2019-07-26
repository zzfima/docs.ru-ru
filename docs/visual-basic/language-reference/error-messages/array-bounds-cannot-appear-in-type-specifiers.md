---
title: В спецификаторах типов не могут задаваться границы массива
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 951f710160ae1023671773c21c73946f5ae94c2b
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512761"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a>В спецификаторах типов не могут задаваться границы массива

Размеры массивов не могут объявляться как часть спецификатора типа данных.

**Идентификатор ошибки:** BC30638

## <a name="to-correct-this-error"></a>Исправление ошибки

- Укажите размер массива, непосредственно следующего за именем переменной, вместо того, чтобы поместить размер массива после типа, как показано в следующем примере.

  ```vb
  Dim Array(8) As Integer
  ```

- Определите массив и инициализируйте его с требуемым количеством элементов, как показано в следующем примере.

  ```vb
  Dim Array2() As Integer = New Integer(8) {}
  ```

## <a name="see-also"></a>См. также

- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
