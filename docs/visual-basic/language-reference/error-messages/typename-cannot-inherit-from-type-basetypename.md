---
title: '&#39;&lt;TypeName&gt; &#39; не может наследовать от &lt;тип&gt; &#39; &lt;имя_базового_типа&gt; &#39; , поскольку он расширяет доступ базового &lt;тип&gt; за пределами сборки'
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: f747b2b24f5fecc22b9e1fbc6ba26b634e9ead2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a><span data-ttu-id="91ff1-102">&#39;&lt;TypeName&gt; &#39; не может наследовать от &lt;тип&gt; &#39; &lt;имя_базового_типа&gt; &#39; , поскольку он расширяет доступ базового &lt;тип&gt; за пределами сборки</span><span class="sxs-lookup"><span data-stu-id="91ff1-102">&#39;&lt;typename&gt;&#39; cannot inherit from &lt;type&gt; &#39;&lt;basetypename&gt;&#39; because it expands the access of the base &lt;type&gt; outside the assembly</span></span>
<span data-ttu-id="91ff1-103">Класс или интерфейс наследует от базового класса или интерфейса, но имеет менее строгий уровень доступа.</span><span class="sxs-lookup"><span data-stu-id="91ff1-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="91ff1-104">Например `Public` интерфейс наследует от `Friend` интерфейса, или `Protected` класс наследует от `Private` класса.</span><span class="sxs-lookup"><span data-stu-id="91ff1-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="91ff1-105">Это предоставляет базовый класс или интерфейс для доступа к выше установленного уровня.</span><span class="sxs-lookup"><span data-stu-id="91ff1-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="91ff1-106">**Идентификатор ошибки:** BC30910</span><span class="sxs-lookup"><span data-stu-id="91ff1-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="91ff1-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="91ff1-107">To correct this error</span></span>  
  
-   <span data-ttu-id="91ff1-108">Измените уровень доступа производный класс или интерфейс был менее строгий, чем базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="91ff1-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="91ff1-109">- или -</span><span class="sxs-lookup"><span data-stu-id="91ff1-109">-or-</span></span>  
  
-   <span data-ttu-id="91ff1-110">Если требуется менее строгий уровень доступа, удалите `Inherits` инструкции.</span><span class="sxs-lookup"><span data-stu-id="91ff1-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="91ff1-111">Не может наследовать от более ограниченный базового класса или интерфейса.</span><span class="sxs-lookup"><span data-stu-id="91ff1-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91ff1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="91ff1-112">See Also</span></span>  
 [<span data-ttu-id="91ff1-113">Оператор Class</span><span class="sxs-lookup"><span data-stu-id="91ff1-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
 [<span data-ttu-id="91ff1-114">Оператор Interface</span><span class="sxs-lookup"><span data-stu-id="91ff1-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="91ff1-115">Оператор Inherits</span><span class="sxs-lookup"><span data-stu-id="91ff1-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="91ff1-116">Уровни доступа в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="91ff1-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
