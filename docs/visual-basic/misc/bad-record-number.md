---
title: Неверный номер записи
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: fbf1a2db97d0474fb758ff5ed572e94395a187da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664761"
---
# <a name="bad-record-number"></a><span data-ttu-id="d0d3e-102">Неверный номер записи</span><span class="sxs-lookup"><span data-stu-id="d0d3e-102">Bad record number</span></span>
<span data-ttu-id="d0d3e-103">Номер записи в операторе `a FileGet`, `FilePut`, `FileGetObject`или `FilePutObject` меньше или равен нулю.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0d3e-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d0d3e-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="d0d3e-105">Проверьте вычисления, используемые при формировании номера записи.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="d0d3e-106">Проверьте правильность написания переменных, содержащих номер записи или используемых при вычислении номеров записей.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="d0d3e-107">Неправильно написанное имя переменной неявно объявляется и приравнивается к нулю, если вы не использовали `Option Explicit On` в модуле.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d3e-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d0d3e-108">See also</span></span>
- [<span data-ttu-id="d0d3e-109">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="d0d3e-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
