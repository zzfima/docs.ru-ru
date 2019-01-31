---
title: Метод доступа Set свойства <propertyname> недоступен
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: 1539eb1652d93402c349c65f77a3edc65b3beb57
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277567"
---
# <a name="set-accessor-of-property-propertyname-is-not-accessible"></a><span data-ttu-id="fbcc6-102">Метод доступа свойства «set» "\<имя_свойства >" не доступен</span><span class="sxs-lookup"><span data-stu-id="fbcc6-102">'Set' accessor of property '\<propertyname>' is not accessible</span></span>
<span data-ttu-id="fbcc6-103">Оператор пытается сохранить значение свойства, если он не имеет доступа к свойству `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="fbcc6-104">Если [инструкция Set](../../../visual-basic/language-reference/statements/set-statement.md) помечается более строгий доступ уровня, чем его [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), попытка задать значение свойства может завершиться ошибкой в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="fbcc6-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="fbcc6-105">`Set` Оператор помечен [частного](../../../visual-basic/language-reference/modifiers/private.md) и вызывающий код находится за пределами класса или структуры, в котором оно определено свойство.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="fbcc6-106">`Set` Оператор помечен [Protected](../../../visual-basic/language-reference/modifiers/protected.md) и вызывающий код находится не в классе или структуре, в котором оно определено свойство, ни в производном классе.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="fbcc6-107">`Set` Оператор помечен [Friend](../../../visual-basic/language-reference/modifiers/friend.md) и вызывающий код не находится в той же сборке, в котором оно определено свойство.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="fbcc6-108">**Идентификатор ошибки:** BC31102</span><span class="sxs-lookup"><span data-stu-id="fbcc6-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fbcc6-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fbcc6-109">To correct this error</span></span>  
  
-   <span data-ttu-id="fbcc6-110">Если у вас есть контроль исходного кода, определяющего свойство, рассмотрим следующее объявление `Set` процедуру с тот же уровень доступа, как и само свойство.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="fbcc6-111">Если у вас нет контроля исходного кода, определяющего свойство или необходимо ограничить `Set` больше, чем у самого свойства, попробуйте переместить оператор, который задает значение свойства в область кода, имеющего более удобный доступ к процедуре уровень доступа свойство.</span><span class="sxs-lookup"><span data-stu-id="fbcc6-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbcc6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="fbcc6-112">See also</span></span>
- [<span data-ttu-id="fbcc6-113">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="fbcc6-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="fbcc6-114">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="fbcc6-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
