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
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="32535-102">В спецификаторах типов не могут задаваться границы массива</span><span class="sxs-lookup"><span data-stu-id="32535-102">Array bounds cannot appear in type specifiers</span></span>

<span data-ttu-id="32535-103">Размеры массивов не могут объявляться как часть спецификатора типа данных.</span><span class="sxs-lookup"><span data-stu-id="32535-103">Array sizes cannot be declared as part of a data type specifier.</span></span>

<span data-ttu-id="32535-104">**Идентификатор ошибки:** BC30638</span><span class="sxs-lookup"><span data-stu-id="32535-104">**Error ID:** BC30638</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="32535-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="32535-105">To correct this error</span></span>

- <span data-ttu-id="32535-106">Укажите размер массива, непосредственно следующего за именем переменной, вместо того, чтобы поместить размер массива после типа, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="32535-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>

  ```vb
  Dim Array(8) As Integer
  ```

- <span data-ttu-id="32535-107">Определите массив и инициализируйте его с требуемым количеством элементов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="32535-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>

  ```vb
  Dim Array2() As Integer = New Integer(8) {}
  ```

## <a name="see-also"></a><span data-ttu-id="32535-108">См. также</span><span class="sxs-lookup"><span data-stu-id="32535-108">See also</span></span>

- [<span data-ttu-id="32535-109">Массивы</span><span class="sxs-lookup"><span data-stu-id="32535-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
