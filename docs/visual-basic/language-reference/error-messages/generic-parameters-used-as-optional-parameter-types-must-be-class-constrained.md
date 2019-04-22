---
title: Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 9b0293472f5eda74c2bf8fb215e15ae5cf8d8b98
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813903"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="6bded-102">Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом</span><span class="sxs-lookup"><span data-stu-id="6bded-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="6bded-103">Процедура объявлена с необязательным параметром, который использует параметр типа, который не должен быть ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="6bded-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="6bded-104">Должно всегда предоставляться значение по умолчанию для каждого необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="6bded-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="6bded-105">Если параметр имеет ссылочный тип, дополнительное значение должно быть `Nothing`, который является допустимое значение для любого ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="6bded-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="6bded-106">Тем не менее если параметр имеет тип значения, этот тип должен быть простой тип данных, ранее определенных Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6bded-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="6bded-107">Это обусловлено составные типы значения, такие как определяемая пользователем структура имеет нет допустимых значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6bded-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="6bded-108">При использовании с параметром типа для необязательного параметра, необходимо гарантировать, что это ссылочного типа во избежание возможного типа значения не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6bded-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="6bded-109">Это означает, что необходимо ограничить параметр типа с помощью `Class` ключевое слово или имя определенного класса.</span><span class="sxs-lookup"><span data-stu-id="6bded-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="6bded-110">**Идентификатор ошибки:** BC32124</span><span class="sxs-lookup"><span data-stu-id="6bded-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6bded-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="6bded-111">To correct this error</span></span>  
  
-   <span data-ttu-id="6bded-112">Ограничить параметр типа для приема только ссылочным типом или не используйте его для необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="6bded-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bded-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6bded-113">See also</span></span>

- [<span data-ttu-id="6bded-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6bded-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="6bded-115">Список типов</span><span class="sxs-lookup"><span data-stu-id="6bded-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="6bded-116">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="6bded-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="6bded-117">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="6bded-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="6bded-118">Структуры</span><span class="sxs-lookup"><span data-stu-id="6bded-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6bded-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="6bded-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
