---
title: '&#39;&lt;Ключевое слово&gt; &#39; допустимо только в методах экземпляров'
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 2d9e26aa7dccf1b9c6390a20a59b10a0d248969d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a><span data-ttu-id="bb84d-102">&#39;&lt;Ключевое слово&gt; &#39; допустимо только в методах экземпляров</span><span class="sxs-lookup"><span data-stu-id="bb84d-102">&#39;&lt;keyword&gt;&#39; is valid only within an instance method</span></span>
<span data-ttu-id="bb84d-103">`Me`, `MyClass`, И `MyBase` ключевые слова ссылаются на конкретные экземпляры класса.</span><span class="sxs-lookup"><span data-stu-id="bb84d-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="bb84d-104">Их нельзя использовать внутри совместно используемого `Function` или `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="bb84d-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="bb84d-105">**Идентификатор ошибки:** BC30043</span><span class="sxs-lookup"><span data-stu-id="bb84d-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bb84d-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bb84d-106">To correct this error</span></span>  
  
-   <span data-ttu-id="bb84d-107">Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.</span><span class="sxs-lookup"><span data-stu-id="bb84d-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb84d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="bb84d-108">See Also</span></span>  
 [<span data-ttu-id="bb84d-109">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="bb84d-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="bb84d-110">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="bb84d-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="bb84d-111">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="bb84d-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
