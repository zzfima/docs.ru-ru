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
# <a name="initializer-expected"></a><span data-ttu-id="f4a73-102">Ожидается инициализатор</span><span class="sxs-lookup"><span data-stu-id="f4a73-102">Initializer expected</span></span>
<span data-ttu-id="f4a73-103">Предпринята попытка объявить экземпляр класса с помощью инициализатора объектов, в котором список инициализации пуст, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f4a73-103">You have tried to declare an instance of a class by using an object initializer in which the initialization list is empty, as shown in the following example.</span></span>  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 <span data-ttu-id="f4a73-104">По крайней мере одно поле или свойство должны быть инициализированы в списке инициализаторов, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f4a73-104">At least one field or property must be initialized in the initializer list, as shown in the following example.</span></span>  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 <span data-ttu-id="f4a73-105">**Идентификатор ошибки:** BC30996</span><span class="sxs-lookup"><span data-stu-id="f4a73-105">**Error ID:** BC30996</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f4a73-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="f4a73-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f4a73-107">Инициализация по крайней мере одно поле или свойство в инициализаторе или не использовать инициализатор объекта.</span><span class="sxs-lookup"><span data-stu-id="f4a73-107">Initialize at least one field or property in the initializer, or do not use an object initializer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a73-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f4a73-108">See also</span></span>

- [<span data-ttu-id="f4a73-109">Инициализаторы объектов. Именованные и анонимные типы</span><span class="sxs-lookup"><span data-stu-id="f4a73-109">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="f4a73-110">Практическое руководство. Объявление объекта с помощью инициализатора объектов</span><span class="sxs-lookup"><span data-stu-id="f4a73-110">How to: Declare an Object by Using an Object Initializer</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
