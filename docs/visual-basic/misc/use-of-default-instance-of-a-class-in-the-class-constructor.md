---
title: Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову
ms.date: 07/20/2015
ms.assetid: 9645b47f-7de5-46d0-bb45-d5fdaa8aaa2a
ms.openlocfilehash: 14c498bf3067415f8de2afaeaaa57cf3f28ae857
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022458"
---
# <a name="use-of-default-instance-of-a-class-in-the-class-constructor-could-lead-to-infinite-recursive-call"></a><span data-ttu-id="0de84-102">Использование экземпляра класса по умолчанию в конструкторе класса может привести к бесконечному рекурсивному вызову</span><span class="sxs-lookup"><span data-stu-id="0de84-102">Use of Default Instance of a class in the class constructor could lead to infinite recursive call</span></span>
<span data-ttu-id="0de84-103">В конструкторе класса использован экземпляр класса по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0de84-103">A default instance of a class has been used in the constructor of the class.</span></span> <span data-ttu-id="0de84-104">Это может привести к бесконечному рекурсивному вызову — бесконечному циклу.</span><span class="sxs-lookup"><span data-stu-id="0de84-104">This can lead to an infinite recursive call, also known as an infinite loop.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0de84-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="0de84-105">To correct this error</span></span>  
  
- <span data-ttu-id="0de84-106">Удалите из конструктора класса экземпляр по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0de84-106">Remove the default instance from the class constructor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de84-107">См. также</span><span class="sxs-lookup"><span data-stu-id="0de84-107">See also</span></span>

- [<span data-ttu-id="0de84-108">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="0de84-108">Constructors</span></span>](~/docs/visual-basic/programming-guide/concepts/object-oriented-programming.md#constructors)
