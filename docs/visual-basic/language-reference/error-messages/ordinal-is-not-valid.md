---
title: Недопустимый порядковый номер
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: f3207c2cc237ae22c295c2b3ed56f18601625226
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822280"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="2ab6c-102">Недопустимый порядковый номер</span><span class="sxs-lookup"><span data-stu-id="2ab6c-102">Ordinal is not valid</span></span>
<span data-ttu-id="2ab6c-103">При вызове библиотеки динамической компоновки (DLL) использовался использовать номер, а не имя процедуры, с помощью `#num` синтаксис.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="2ab6c-104">Эта ошибка имеет следующие возможные причины:</span><span class="sxs-lookup"><span data-stu-id="2ab6c-104">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="2ab6c-105">Попытка преобразовать `#num` выражение в порядковый.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
-   <span data-ttu-id="2ab6c-106">`#num` Указанного не соответствует ни одной функции в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
-   <span data-ttu-id="2ab6c-107">Библиотеку типов имеет недопустимое объявление приводит к внутреннего использования недопустимого порядкового номера.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2ab6c-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="2ab6c-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="2ab6c-109">Убедитесь, что выражение представляет допустимый номер, или вызовите процедуру по имени.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2.  <span data-ttu-id="2ab6c-110">Убедитесь, что `#num` определяет допустимую функцию в библиотеке DLL.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3.  <span data-ttu-id="2ab6c-111">Изолируйте проблемный закомментировать код вызова процедуры.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="2ab6c-112">Запись `Declare` инструкции для процедуры и сообщите об ошибке разработчику библиотеки типов.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab6c-113">См. также</span><span class="sxs-lookup"><span data-stu-id="2ab6c-113">See also</span></span>

- [<span data-ttu-id="2ab6c-114">Оператор Declare</span><span class="sxs-lookup"><span data-stu-id="2ab6c-114">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
