---
title: <keyword> разрешено использовать только в методе экземпляра
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 5ff82b932f9bea4c7fd087651e34277ef94bc27c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946644"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="e3f6a-102">"\<ключевое слово >" является допустимым только в методе экземпляра</span><span class="sxs-lookup"><span data-stu-id="e3f6a-102">'\<keyword>' is valid only within an instance method</span></span>
<span data-ttu-id="e3f6a-103">`Me`, `MyClass`, И `MyBase` ключевые слова ссылаются на экземпляры определенного класса.</span><span class="sxs-lookup"><span data-stu-id="e3f6a-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="e3f6a-104">Их нельзя использовать внутри совместно используемого `Function` или `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="e3f6a-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="e3f6a-105">**Идентификатор ошибки:** BC30043</span><span class="sxs-lookup"><span data-stu-id="e3f6a-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e3f6a-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e3f6a-106">To correct this error</span></span>  
  
- <span data-ttu-id="e3f6a-107">Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.</span><span class="sxs-lookup"><span data-stu-id="e3f6a-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3f6a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e3f6a-108">See also</span></span>

- [<span data-ttu-id="e3f6a-109">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="e3f6a-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="e3f6a-110">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="e3f6a-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="e3f6a-111">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="e3f6a-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
