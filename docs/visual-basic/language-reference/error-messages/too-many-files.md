---
title: "Слишком много файлов"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID67
ms.assetid: 2ff203e2-bba6-43ae-b72f-8e92a881c98f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 506f0735956267d51b575cd26b628605e9db38cc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="too-many-files"></a><span data-ttu-id="69227-102">Слишком много файлов</span><span class="sxs-lookup"><span data-stu-id="69227-102">Too many files</span></span>
<span data-ttu-id="69227-103">Дополнительные файлы были созданы в корневом каталоге превышает операционной системы либо открытых файлов превышает число, заданное в **файлов =** в файле CONFIG. Файл SYS.</span><span class="sxs-lookup"><span data-stu-id="69227-103">Either more files have been created in the root directory than the operating system permits, or more files have been opened than the number specified in the **files=** setting in your CONFIG.SYS file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69227-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="69227-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="69227-105">Если программа открытие, закрытие или сохранение файлов в корневом каталоге, измените ее, чтобы он использовал подкаталог.</span><span class="sxs-lookup"><span data-stu-id="69227-105">If your program is opening, closing, or saving files in the root directory, change your program so that it uses a subdirectory.</span></span>  
  
2.  <span data-ttu-id="69227-106">Увеличьте число файлов, указанных в вашей **файлов =** в файле CONFIG. SYS и перезапустите компьютер.</span><span class="sxs-lookup"><span data-stu-id="69227-106">Increase the number of files specified in your **files=** setting in your CONFIG.SYS file, and restart your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69227-107">См. также</span><span class="sxs-lookup"><span data-stu-id="69227-107">See Also</span></span>  
 [<span data-ttu-id="69227-108">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="69227-108">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
