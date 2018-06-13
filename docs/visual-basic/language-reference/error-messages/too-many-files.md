---
title: Слишком много файлов
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 8a9d89cc96e5b5875d0286becbf5b20d6895ae34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593971"
---
# <a name="too-many-files"></a><span data-ttu-id="d077f-102">Слишком много файлов</span><span class="sxs-lookup"><span data-stu-id="d077f-102">Too many files</span></span>
<span data-ttu-id="d077f-103">Дополнительные файлы были созданы в корневом каталоге превышает операционной системы либо открытых файлов превышает число, заданное в **файлов =** в файле CONFIG. Файл SYS.</span><span class="sxs-lookup"><span data-stu-id="d077f-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d077f-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d077f-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="d077f-105">Если программа открытие, закрытие или сохранение файлов в корневом каталоге, измените ее, чтобы он использовал подкаталог.</span><span class="sxs-lookup"><span data-stu-id="d077f-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2.  <span data-ttu-id="d077f-106">Увеличьте число файлов, указанных в вашей **файлов =** в файле CONFIG. SYS и перезапустите компьютер.</span><span class="sxs-lookup"><span data-stu-id="d077f-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d077f-107">См. также</span><span class="sxs-lookup"><span data-stu-id="d077f-107">See Also</span></span>  
 [<span data-ttu-id="d077f-108">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="d077f-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
