---
title: "Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords: BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a13ea66f12e54db4e585577e20e1f5396669f1a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="ba4f9-102">Универсальные параметры, используемые как типы необязательных параметров, должны быть ограничены классом</span><span class="sxs-lookup"><span data-stu-id="ba4f9-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="ba4f9-103">Процедура объявлена с необязательным параметром, который использует параметр типа, который не обязательно должен быть ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="ba4f9-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="ba4f9-104">Всегда необходимо указывать значение по умолчанию для каждого необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="ba4f9-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="ba4f9-105">Если параметр имеет ссылочный тип, дополнительное значение должно быть `Nothing`, которое является допустимым для любого ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="ba4f9-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="ba4f9-106">Тем не менее если параметр имеет тип значения, этот тип должен быть простой тип данных, ранее определенных Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ba4f9-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="ba4f9-107">Это объясняется значение составного типа, например пользовательской структуры имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ba4f9-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="ba4f9-108">При использовании параметра типа для необязательного параметра, необходимо гарантировать, что это ссылочного типа во избежание типа значения и не имеет значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ba4f9-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="ba4f9-109">Это означает, что необходимо ограничить параметр типа с помощью `Class` ключевое слово или имя определенного класса.</span><span class="sxs-lookup"><span data-stu-id="ba4f9-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="ba4f9-110">**Идентификатор ошибки:** BC32124</span><span class="sxs-lookup"><span data-stu-id="ba4f9-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ba4f9-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ba4f9-111">To correct this error</span></span>  
  
-   <span data-ttu-id="ba4f9-112">Ограничить параметр типа гарантированно принимает ссылочный тип или не используйте его для необязательного параметра.</span><span class="sxs-lookup"><span data-stu-id="ba4f9-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4f9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ba4f9-113">See Also</span></span>  
 [<span data-ttu-id="ba4f9-114">Универсальные типы в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ba4f9-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="ba4f9-115">Список типов</span><span class="sxs-lookup"><span data-stu-id="ba4f9-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="ba4f9-116">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="ba4f9-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="ba4f9-117">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="ba4f9-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="ba4f9-118">Структуры</span><span class="sxs-lookup"><span data-stu-id="ba4f9-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="ba4f9-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="ba4f9-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
