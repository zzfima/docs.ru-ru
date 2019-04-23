---
title: Неверный номер записи
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: abd0a1467c0991a40b93e74a1d7a7889367fb8ca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340806"
---
# <a name="bad-record-number"></a><span data-ttu-id="358b6-102">Неверный номер записи</span><span class="sxs-lookup"><span data-stu-id="358b6-102">Bad record number</span></span>
<span data-ttu-id="358b6-103">Номер записи в операторе `a FileGet`, `FilePut`, `FileGetObject`или `FilePutObject` меньше или равен нулю.</span><span class="sxs-lookup"><span data-stu-id="358b6-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="358b6-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="358b6-104">To correct this error</span></span>  
  
1. <span data-ttu-id="358b6-105">Проверьте вычисления, используемые при формировании номера записи.</span><span class="sxs-lookup"><span data-stu-id="358b6-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="358b6-106">Проверьте правильность написания переменных, содержащих номер записи или используемых при вычислении номеров записей.</span><span class="sxs-lookup"><span data-stu-id="358b6-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="358b6-107">Неправильно написанное имя переменной неявно объявляется и приравнивается к нулю, если вы не использовали `Option Explicit On` в модуле.</span><span class="sxs-lookup"><span data-stu-id="358b6-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="358b6-108">См. также</span><span class="sxs-lookup"><span data-stu-id="358b6-108">See also</span></span>

- [<span data-ttu-id="358b6-109">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="358b6-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
