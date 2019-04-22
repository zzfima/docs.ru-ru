---
title: <typename> не может наследоваться от <type><basetypename>, поскольку он расширяет доступ базового типа <type> за пределы сборки
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: dc979a66c73fdf15a4349a003680156e0ce27ed3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838954"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="b7f72-102">"\<typename >" не может наследовать от \<тип > "\<имя_базового_типа >", поскольку он расширяет доступ базового \<тип > за пределы данной сборки</span><span class="sxs-lookup"><span data-stu-id="b7f72-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="b7f72-103">Класс или интерфейс наследует от базового класса или интерфейса, но имеет менее строгий уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="b7f72-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="b7f72-104">Например `Public` интерфейс наследует от `Friend` интерфейс, или `Protected` класс наследует от `Private` класса.</span><span class="sxs-lookup"><span data-stu-id="b7f72-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="b7f72-105">Этот класс представляет базовый класс или интерфейс для доступа к выше установленного уровня.</span><span class="sxs-lookup"><span data-stu-id="b7f72-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="b7f72-106">**Идентификатор ошибки:** BC30910</span><span class="sxs-lookup"><span data-stu-id="b7f72-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b7f72-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b7f72-107">To correct this error</span></span>  
  
-   <span data-ttu-id="b7f72-108">Измените уровень доступа производный класс или интерфейс был менее строгий, как и для базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b7f72-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="b7f72-109">-или-</span><span class="sxs-lookup"><span data-stu-id="b7f72-109">-or-</span></span>  
  
-   <span data-ttu-id="b7f72-110">Если требуется менее строгий уровень доступа, удалите `Inherits` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b7f72-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="b7f72-111">Не может наследовать от более ограниченных базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b7f72-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7f72-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b7f72-112">See also</span></span>

- [<span data-ttu-id="b7f72-113">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="b7f72-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="b7f72-114">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="b7f72-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="b7f72-115">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="b7f72-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="b7f72-116">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7f72-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
