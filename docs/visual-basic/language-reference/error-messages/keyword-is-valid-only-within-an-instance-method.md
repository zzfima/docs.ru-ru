---
title: <keyword> разрешено использовать только в методе экземпляра
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 8ec1e704815ee10cb98d8cc20fb5982ee4b92832
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662013"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a><span data-ttu-id="1afc4-102">"\<ключевое слово >" является допустимым только в методе экземпляра</span><span class="sxs-lookup"><span data-stu-id="1afc4-102">'\<keyword>' is valid only within an instance method</span></span>
<span data-ttu-id="1afc4-103">`Me`, `MyClass`, И `MyBase` ключевые слова ссылаются на экземпляры определенного класса.</span><span class="sxs-lookup"><span data-stu-id="1afc4-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="1afc4-104">Их нельзя использовать внутри совместно используемого `Function` или `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="1afc4-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="1afc4-105">**Идентификатор ошибки:** BC30043</span><span class="sxs-lookup"><span data-stu-id="1afc4-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1afc4-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="1afc4-106">To correct this error</span></span>  
  
- <span data-ttu-id="1afc4-107">Удалите ключевое слово из процедуры или удалите `Shared` ключевое слово из объявления процедуры.</span><span class="sxs-lookup"><span data-stu-id="1afc4-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1afc4-108">См. также</span><span class="sxs-lookup"><span data-stu-id="1afc4-108">See also</span></span>

- [<span data-ttu-id="1afc4-109">Присваивание объектных переменных</span><span class="sxs-lookup"><span data-stu-id="1afc4-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="1afc4-110">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="1afc4-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [<span data-ttu-id="1afc4-111">Основы наследования</span><span class="sxs-lookup"><span data-stu-id="1afc4-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
