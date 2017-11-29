---
title: "Неверный номер записи"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be04987353498775ec7dcef50b6acc1e6b4ec149
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="bad-record-number"></a><span data-ttu-id="e06e7-102">Неверный номер записи</span><span class="sxs-lookup"><span data-stu-id="e06e7-102">Bad record number</span></span>
<span data-ttu-id="e06e7-103">Номер записи в операторе `a FileGet`, `FilePut`, `FileGetObject`или `FilePutObject` меньше или равен нулю.</span><span class="sxs-lookup"><span data-stu-id="e06e7-103">The record number in `a FileGet`, `FilePut`, `FileGetObject`, or `FilePutObject` statement is less than or equal to zero.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e06e7-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e06e7-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="e06e7-105">Проверьте вычисления, используемые при формировании номера записи.</span><span class="sxs-lookup"><span data-stu-id="e06e7-105">Check the calculations used in generating the record number.</span></span> <span data-ttu-id="e06e7-106">Проверьте правильность написания переменных, содержащих номер записи или используемых при вычислении номеров записей.</span><span class="sxs-lookup"><span data-stu-id="e06e7-106">Verify spelling of the variables containing the record number or used in calculating record numbers.</span></span> <span data-ttu-id="e06e7-107">Неправильно написанное имя переменной неявно объявляется и приравнивается к нулю, если вы не использовали `Option Explicit On` в модуле.</span><span class="sxs-lookup"><span data-stu-id="e06e7-107">A misspelled variable name is implicitly declared and initialized to zero, unless you used `Option Explicit On` in the module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e06e7-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e06e7-108">See Also</span></span>  
 [<span data-ttu-id="e06e7-109">Оператор Option Explicit</span><span class="sxs-lookup"><span data-stu-id="e06e7-109">Option Explicit Statement</span></span>](../../visual-basic/language-reference/statements/option-explicit-statement.md)
