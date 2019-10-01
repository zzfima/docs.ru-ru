---
title: Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: 9e8bb7b79b5a770c3c92e47d8e7c01c5b83d6061
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701207"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="ac393-102">Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером</span><span class="sxs-lookup"><span data-stu-id="ac393-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="ac393-103">Цикл `For Each` использует массив в качестве переменной итерации *элемента* , но инициализирует этот массив.</span><span class="sxs-lookup"><span data-stu-id="ac393-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="ac393-104">Следующие инструкции показывают, как можно создать эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="ac393-104">The following statements show how this error can be generated.</span></span>  
  
```vb  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="ac393-105">Первая инструкция `For Each` является правильным способом доступа к элементам `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="ac393-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="ac393-106">Вторая инструкция `For Each` вызывает эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="ac393-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="ac393-107">**Идентификатор ошибки:** BC32039</span><span class="sxs-lookup"><span data-stu-id="ac393-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac393-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ac393-108">To correct this error</span></span>  
  
- <span data-ttu-id="ac393-109">Удалите инициализацию из объявления переменной итерации *элемента* .</span><span class="sxs-lookup"><span data-stu-id="ac393-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac393-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ac393-110">See also</span></span>

- [<span data-ttu-id="ac393-111">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="ac393-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="ac393-112">Массивы</span><span class="sxs-lookup"><span data-stu-id="ac393-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="ac393-113">Коллекции</span><span class="sxs-lookup"><span data-stu-id="ac393-113">Collections</span></span>](../../../standard/collections/index.md)
