---
title: Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 7e2b59f758ef236717a912694576b514e2ae8a60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="60b8b-102">Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом</span><span class="sxs-lookup"><span data-stu-id="60b8b-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="60b8b-103">Процедура объявлена с необязательным параметром, который использует параметр типа, который не обязательно должен быть ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="60b8b-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="60b8b-104">Всегда необходимо указывать значение по умолчанию для каждого необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="60b8b-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="60b8b-105">Если параметр имеет ссылочный тип, дополнительное значение должно быть `Nothing`, которое является допустимым для любого ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="60b8b-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="60b8b-106">Тем не менее если параметр имеет тип значения, этот тип должен быть простой тип данных, ранее определенных Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="60b8b-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="60b8b-107">Это объясняется значение составного типа, например пользовательской структуры имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60b8b-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="60b8b-108">При использовании параметра типа для необязательного параметра, необходимо гарантировать, что это ссылочного типа во избежание типа значения и не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="60b8b-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="60b8b-109">Это означает, что необходимо ограничить параметр типа с помощью `Class` ключевое слово или имя определенного класса.</span><span class="sxs-lookup"><span data-stu-id="60b8b-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="60b8b-110">**Идентификатор ошибки:** BC32124</span><span class="sxs-lookup"><span data-stu-id="60b8b-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="60b8b-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="60b8b-111">To correct this error</span></span>  
  
-   <span data-ttu-id="60b8b-112">Ограничить параметр типа гарантированно принимает ссылочный тип или не используйте его для необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="60b8b-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b8b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="60b8b-113">See Also</span></span>  
 [<span data-ttu-id="60b8b-114">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60b8b-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="60b8b-115">Список типов</span><span class="sxs-lookup"><span data-stu-id="60b8b-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="60b8b-116">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="60b8b-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="60b8b-117">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="60b8b-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="60b8b-118">Структуры</span><span class="sxs-lookup"><span data-stu-id="60b8b-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="60b8b-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="60b8b-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
