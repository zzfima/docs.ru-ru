---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 75a08b411a4afd7ea8e11953f1d465b082faa712
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="file-already-open"></a><span data-ttu-id="cd2d7-102">Файл уже открыт</span><span class="sxs-lookup"><span data-stu-id="cd2d7-102">File already open</span></span>
<span data-ttu-id="cd2d7-103">В некоторых случаях файл необходимо закрыть перед другим `FileOpen` или другую операцию.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="cd2d7-104">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="cd2d7-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="cd2d7-105">Режим последовательного вывода `FileOpen` операция была выполнена для файла, который уже открыт</span><span class="sxs-lookup"><span data-stu-id="cd2d7-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="cd2d7-106">Оператор ссылается на открытый файл.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cd2d7-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cd2d7-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="cd2d7-108">Закройте файл перед выполнением инструкции.</span><span class="sxs-lookup"><span data-stu-id="cd2d7-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd2d7-109">См. также</span><span class="sxs-lookup"><span data-stu-id="cd2d7-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
