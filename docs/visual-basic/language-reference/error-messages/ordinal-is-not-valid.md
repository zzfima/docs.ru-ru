---
title: Недопустимый порядковый номер
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 351b7ee7f1cfc5199d878c33965770693227ccc4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618967"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="e1e05-102">Недопустимый порядковый номер</span><span class="sxs-lookup"><span data-stu-id="e1e05-102">Ordinal is not valid</span></span>
<span data-ttu-id="e1e05-103">При вызове библиотеки динамической компоновки (DLL) использовался использовать номер, а не имя процедуры, с помощью `#num` синтаксис.</span><span class="sxs-lookup"><span data-stu-id="e1e05-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="e1e05-104">Эта ошибка имеет следующие возможные причины:</span><span class="sxs-lookup"><span data-stu-id="e1e05-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="e1e05-105">Попытка преобразовать `#num` выражение в порядковый.</span><span class="sxs-lookup"><span data-stu-id="e1e05-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="e1e05-106">`#num` Указанного не соответствует ни одной функции в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="e1e05-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="e1e05-107">Библиотеку типов имеет недопустимое объявление приводит к внутреннего использования недопустимого порядкового номера.</span><span class="sxs-lookup"><span data-stu-id="e1e05-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e1e05-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e1e05-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="e1e05-109">Убедитесь, что выражение представляет допустимый номер, или вызовите процедуру по имени.</span><span class="sxs-lookup"><span data-stu-id="e1e05-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="e1e05-110">Убедитесь, что `#num` определяет допустимую функцию в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="e1e05-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="e1e05-111">Изолируйте проблемный закомментировать код вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="e1e05-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="e1e05-112">Запись `Declare` инструкции для процедуры и сообщите об ошибке разработчику библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="e1e05-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1e05-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e1e05-113">See also</span></span>
- [<span data-ttu-id="e1e05-114">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="e1e05-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
