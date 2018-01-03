---
title: "Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords: BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef36f14d5323a4592afe59573e249d8cfb218df9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="2cb22-102">Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером</span><span class="sxs-lookup"><span data-stu-id="2cb22-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="2cb22-103">Объект `For Each` цикл использует массив в качестве его *элемент* переменной итерации, но инициализирует этот массив.</span><span class="sxs-lookup"><span data-stu-id="2cb22-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="2cb22-104">Следующие инструкции показывают, как эта ошибка может быть создано.</span><span class="sxs-lookup"><span data-stu-id="2cb22-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="2cb22-105">Первый `For Each` инструкция является правильный способ доступа к элементам `arrayList`.</span><span class="sxs-lookup"><span data-stu-id="2cb22-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="2cb22-106">Второй `For Each` инструкция создает эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="2cb22-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="2cb22-107">**Идентификатор ошибки:** BC32039</span><span class="sxs-lookup"><span data-stu-id="2cb22-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2cb22-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2cb22-108">To correct this error</span></span>  
  
-   <span data-ttu-id="2cb22-109">Удалите инициализацию из объявления *элемент* переменной итерации.</span><span class="sxs-lookup"><span data-stu-id="2cb22-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb22-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2cb22-110">See Also</span></span>  
 [<span data-ttu-id="2cb22-111">Оператор For...Next</span><span class="sxs-lookup"><span data-stu-id="2cb22-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="2cb22-112">Массивы</span><span class="sxs-lookup"><span data-stu-id="2cb22-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="2cb22-113">Коллекции</span><span class="sxs-lookup"><span data-stu-id="2cb22-113">Collections</span></span>](../../../standard/collections/index.md)
