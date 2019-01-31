---
title: <typename> не может наследоваться от <type><basetypename>, поскольку он расширяет доступ базового типа <type> за пределы сборки
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 226c85f887ecc706a5cb554c2163742f10896141
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269826"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="ad26e-102">"\<typename >" не может наследовать от \<тип > "\<имя_базового_типа >", поскольку он расширяет доступ базового \<тип > за пределы данной сборки</span><span class="sxs-lookup"><span data-stu-id="ad26e-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="ad26e-103">Класс или интерфейс наследует от базового класса или интерфейса, но имеет менее строгий уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="ad26e-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="ad26e-104">Например `Public` интерфейс наследует от `Friend` интерфейс, или `Protected` класс наследует от `Private` класса.</span><span class="sxs-lookup"><span data-stu-id="ad26e-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="ad26e-105">Этот класс представляет базовый класс или интерфейс для доступа к выше установленного уровня.</span><span class="sxs-lookup"><span data-stu-id="ad26e-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="ad26e-106">**Идентификатор ошибки:** BC30910</span><span class="sxs-lookup"><span data-stu-id="ad26e-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ad26e-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ad26e-107">To correct this error</span></span>  
  
-   <span data-ttu-id="ad26e-108">Измените уровень доступа производный класс или интерфейс был менее строгий, как и для базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ad26e-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="ad26e-109">- или -</span><span class="sxs-lookup"><span data-stu-id="ad26e-109">-or-</span></span>  
  
-   <span data-ttu-id="ad26e-110">Если требуется менее строгий уровень доступа, удалите `Inherits` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ad26e-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="ad26e-111">Не может наследовать от более ограниченных базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="ad26e-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad26e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ad26e-112">See also</span></span>
- [<span data-ttu-id="ad26e-113">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="ad26e-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="ad26e-114">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="ad26e-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="ad26e-115">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="ad26e-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="ad26e-116">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ad26e-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
