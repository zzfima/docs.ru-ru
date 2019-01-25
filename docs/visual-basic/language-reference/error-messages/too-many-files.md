---
title: Слишком много файлов
ms.date: 07/20/2015
f1_keywords:
- vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
ms.openlocfilehash: 15e08cedbd58016959f00e1ca817019937775df2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737235"
---
# <a name="too-many-files"></a><span data-ttu-id="5e157-102">Слишком много файлов</span><span class="sxs-lookup"><span data-stu-id="5e157-102">Too many files</span></span>
<span data-ttu-id="5e157-103">Дополнительные файлы были созданы в корневом каталоге превышает допустимое для операционной системы, либо открытых больше файлов превышает число, указанное в **файлов =** в файле CONFIG. Файл SYS.</span><span class="sxs-lookup"><span data-stu-id="5e157-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5e157-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="5e157-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="5e157-105">Если программа открытие, закрытие или сохранение файлов в корневом каталоге, измените ее так, чтобы использовалось подкаталог.</span><span class="sxs-lookup"><span data-stu-id="5e157-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2.  <span data-ttu-id="5e157-106">Увеличить количество файлов, указанных в вашей **файлов =** в файле CONFIG. SYS и перезапустите компьютер.</span><span class="sxs-lookup"><span data-stu-id="5e157-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e157-107">См. также</span><span class="sxs-lookup"><span data-stu-id="5e157-107">See also</span></span>
- [<span data-ttu-id="5e157-108">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="5e157-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
