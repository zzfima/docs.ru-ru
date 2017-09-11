---
title: "WithEvents (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.WithEvents
- WithEvents
dev_langs:
- VB
helpviewer_keywords:
- WithEvents keyword
ms.assetid: 19d461f5-d72f-4de9-8c1d-0a6650316990
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b956f8f0d6f0a2fd9f41c5df6d6c82b43fa09018
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="withevents-visual-basic"></a><span data-ttu-id="0e18c-102">WithEvents (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e18c-102">WithEvents (Visual Basic)</span></span>
<span data-ttu-id="0e18c-103">Указывает, что один или несколько переменных объявленного члена относится к экземпляру класса, который может порождать события.</span><span class="sxs-lookup"><span data-stu-id="0e18c-103">Specifies that one or more declared member variables refer to an instance of a class that can raise events.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e18c-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e18c-104">Remarks</span></span>  
 <span data-ttu-id="0e18c-105">Если переменная определена с помощью `WithEvents`, можно декларативно указать, что метод обрабатывает события переменной с помощью `Handles` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0e18c-105">When a variable is defined using `WithEvents`, you can declaratively specify that a method handles the variable's events using the `Handles` keyword.</span></span>  
  
 <span data-ttu-id="0e18c-106">Можно использовать `WithEvents` только на уровне класса или модуля.</span><span class="sxs-lookup"><span data-stu-id="0e18c-106">You can use `WithEvents` only at class or module level.</span></span> <span data-ttu-id="0e18c-107">Это означает, что контекст объявления для `WithEvents` переменной должен быть классом или модулем и не может быть исходным файлом, пространство имен, структуры или процедуры.</span><span class="sxs-lookup"><span data-stu-id="0e18c-107">This means the declaration context for a `WithEvents` variable must be a class or module and cannot be a source file, namespace, structure, or procedure.</span></span>  
  
 <span data-ttu-id="0e18c-108">Нельзя использовать `WithEvents` для членов структуры.</span><span class="sxs-lookup"><span data-stu-id="0e18c-108">You cannot use `WithEvents` on a structure member.</span></span>  
  
 <span data-ttu-id="0e18c-109">Можно объявлять только отдельные переменные — не массивы — с `WithEvents`.</span><span class="sxs-lookup"><span data-stu-id="0e18c-109">You can declare only individual variables—not arrays—with `WithEvents`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="0e18c-110">Правила</span><span class="sxs-lookup"><span data-stu-id="0e18c-110">Rules</span></span>  
  
-   <span data-ttu-id="0e18c-111">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="0e18c-111">**Element Types.**</span></span> <span data-ttu-id="0e18c-112">Необходимо объявить `WithEvents` переменные объектные переменные, что позволяет им принимать экземпляры классов.</span><span class="sxs-lookup"><span data-stu-id="0e18c-112">You must declare `WithEvents` variables to be object variables so that they can accept class instances.</span></span> <span data-ttu-id="0e18c-113">Однако нельзя объявлять их как `Object`.</span><span class="sxs-lookup"><span data-stu-id="0e18c-113">However, you cannot declare them as `Object`.</span></span> <span data-ttu-id="0e18c-114">Их необходимо объявить как определенный класс, который может инициировать события.</span><span class="sxs-lookup"><span data-stu-id="0e18c-114">You must declare them as the specific class that can raise the events.</span></span>  
  
 <span data-ttu-id="0e18c-115">`WithEvents` Модификатор может использоваться в этом контексте: [в операторе Dim](../../../visual-basic/language-reference/statements/dim-statement.md)</span><span class="sxs-lookup"><span data-stu-id="0e18c-115">The `WithEvents` modifier can be used in this context: [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e18c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0e18c-116">See Also</span></span>  
 <span data-ttu-id="0e18c-117">[Обрабатывает](../../../visual-basic/language-reference/statements/handles-clause.md) </span><span class="sxs-lookup"><span data-stu-id="0e18c-117">[Handles](../../../visual-basic/language-reference/statements/handles-clause.md) </span></span>  
<span data-ttu-id="0e18c-118"> [Ключевые слова](../../../visual-basic/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0e18c-118"> [Keywords](../../../visual-basic/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="0e18c-119"> [События](../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="0e18c-119"> [Events](../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
