---
title: Аргумент NPer должен быть больше нуля
ms.date: 07/20/2015
f1_keywords:
- vbrRate_NPerMustBeGTZero
ms.assetid: d49242df-dbd1-4b26-bd8c-ed56d24fdfcd
ms.openlocfilehash: 6f54a2da0eb0c1cc31a4aa536fdcb59026240a25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61977149"
---
# <a name="argument-nper-must-be-greater-than-zero"></a><span data-ttu-id="fdaff-102">Аргумент NPer должен быть больше нуля</span><span class="sxs-lookup"><span data-stu-id="fdaff-102">Argument 'NPer' must be greater than zero</span></span>
<span data-ttu-id="fdaff-103">Функция `NPer` , которая возвращает значение `Double` , определяющее количество периодов для ежегодного дохода на основе периодических фиксированных выплат и фиксированной процентной ставки, требует аргумент, значение которого больше нуля.</span><span class="sxs-lookup"><span data-stu-id="fdaff-103">The `NPer` function, which returns a `Double` specifying the number of periods for an annuity based on periodic fixed payments and a fixed interest rate, requires an argument greater than zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fdaff-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fdaff-104">To correct this error</span></span>  
  
- <span data-ttu-id="fdaff-105">Проверьте правильность написания аргументов в выражении.</span><span class="sxs-lookup"><span data-stu-id="fdaff-105">Check the spelling of arguments in the expression.</span></span> <span data-ttu-id="fdaff-106">Неправильно написанное имя переменной может привести к неявному созданию числовой переменной, которая инициализируется нулевым значением.</span><span class="sxs-lookup"><span data-stu-id="fdaff-106">A misspelled variable name can implicitly create a numeric variable that is initialized to zero.</span></span>  
  
- <span data-ttu-id="fdaff-107">Проверьте предыдущие операции с переменными в выражении, в особенности те, которые передавались в процедуру как аргументы из других процедур.</span><span class="sxs-lookup"><span data-stu-id="fdaff-107">Check previous operations on variables in the expression, especially those passed into the procedure as arguments from other procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdaff-108">См. также</span><span class="sxs-lookup"><span data-stu-id="fdaff-108">See also</span></span>

- [<span data-ttu-id="fdaff-109">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="fdaff-109">Passing Arguments by Value and by Reference</span></span>](../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
