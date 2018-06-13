---
title: '&#39;Задать&#39; метод доступа свойства &#39; &lt;propertyname&gt; &#39; недоступен'
ms.date: 07/20/2015
f1_keywords:
- vbc31102
- bc31102
helpviewer_keywords:
- BC31102
ms.assetid: 6f7b31b7-3656-4ae1-8851-90f5f4c6950a
ms.openlocfilehash: d047d03755de89d4740482db4845d5db72003ac0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595856"
---
# <a name="39set39-accessor-of-property-39ltpropertynamegt39-is-not-accessible"></a><span data-ttu-id="cd614-102">&#39;Задать&#39; метод доступа свойства &#39; &lt;propertyname&gt; &#39; недоступен</span><span class="sxs-lookup"><span data-stu-id="cd614-102">&#39;Set&#39; accessor of property &#39;&lt;propertyname&gt;&#39; is not accessible</span></span>
<span data-ttu-id="cd614-103">Оператор пытается сохранить значение свойства, если он не имеет доступа к свойству `Set` процедуры.</span><span class="sxs-lookup"><span data-stu-id="cd614-103">A statement attempts to store the value of a property when it does not have access to the property's `Set` procedure.</span></span>  
  
 <span data-ttu-id="cd614-104">Если [инструкции Set](../../../visual-basic/language-reference/statements/set-statement.md) помечается более строгий доступ уровня, чем его [оператор Property](../../../visual-basic/language-reference/statements/property-statement.md), попытка задать значение свойства может завершиться ошибкой в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="cd614-104">If the [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) is marked with a more restrictive access level than its [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md), an attempt to set the property value could fail in the following cases:</span></span>  
  
-   <span data-ttu-id="cd614-105">`Set` Оператор помечен [закрытый](../../../visual-basic/language-reference/modifiers/private.md) и вызывающий код находится за пределами класса или структуры, в котором определено свойство.</span><span class="sxs-lookup"><span data-stu-id="cd614-105">The `Set` statement is marked [Private](../../../visual-basic/language-reference/modifiers/private.md) and the calling code is outside the class or structure in which the property is defined.</span></span>  
  
-   <span data-ttu-id="cd614-106">`Set` Оператор помечен [Protected](../../../visual-basic/language-reference/modifiers/protected.md) и вызывающий код находится не в классе или структуре, в котором определено свойство, ни в производном классе.</span><span class="sxs-lookup"><span data-stu-id="cd614-106">The `Set` statement is marked [Protected](../../../visual-basic/language-reference/modifiers/protected.md) and the calling code is not in the class or structure in which the property is defined, nor in a derived class.</span></span>  
  
-   <span data-ttu-id="cd614-107">`Set` Оператор помечен [Friend](../../../visual-basic/language-reference/modifiers/friend.md) и вызывающий код не находится в той же сборке, в котором определено свойство.</span><span class="sxs-lookup"><span data-stu-id="cd614-107">The `Set` statement is marked [Friend](../../../visual-basic/language-reference/modifiers/friend.md) and the calling code is not in the same assembly in which the property is defined.</span></span>  
  
 <span data-ttu-id="cd614-108">**Идентификатор ошибки:** BC31102</span><span class="sxs-lookup"><span data-stu-id="cd614-108">**Error ID:** BC31102</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd614-109">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cd614-109">To correct this error</span></span>  
  
-   <span data-ttu-id="cd614-110">Если вы управляете исходного кода, определяющего свойство, рассмотрите возможность объявления `Set` процедуру с тем же уровнем доступа, как и само свойство.</span><span class="sxs-lookup"><span data-stu-id="cd614-110">If you have control of the source code defining the property, consider declaring the `Set` procedure with the same access level as the property itself.</span></span>  
  
-   <span data-ttu-id="cd614-111">Если вы не управляете исходного кода, определяющего свойство или необходимо ограничить `Set` уровень доступа процедуры больше, чем к самому свойству, попробуйте переместить инструкцию, которая задает значение свойства в область кода, имеющего более удобный доступ к свойство.</span><span class="sxs-lookup"><span data-stu-id="cd614-111">If you do not have control of the source code defining the property, or you must restrict the `Set` procedure access level more than the property itself, try to move the statement that sets the property value to a region of code that has better access to the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd614-112">См. также</span><span class="sxs-lookup"><span data-stu-id="cd614-112">See Also</span></span>  
 [<span data-ttu-id="cd614-113">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="cd614-113">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [<span data-ttu-id="cd614-114">Практическое руководство. Объявление свойства со смешанным уровнем доступа</span><span class="sxs-lookup"><span data-stu-id="cd614-114">How to: Declare a Property with Mixed Access Levels</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)
