---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770364"
---
# <a name="file-already-open"></a><span data-ttu-id="889ab-102">Файл уже открыт</span><span class="sxs-lookup"><span data-stu-id="889ab-102">File already open</span></span>
<span data-ttu-id="889ab-103">Иногда файл должен быть закрыт перед другим `FileOpen` или другую операцию.</span><span class="sxs-lookup"><span data-stu-id="889ab-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="889ab-104">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="889ab-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="889ab-105">Режим последовательного вывода `FileOpen` операция была выполнена для файла, который уже открыт</span><span class="sxs-lookup"><span data-stu-id="889ab-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="889ab-106">Оператор ссылается на открытый файл.</span><span class="sxs-lookup"><span data-stu-id="889ab-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="889ab-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="889ab-107">To correct this error</span></span>  
  
1. <span data-ttu-id="889ab-108">Закройте файл перед выполнением инструкции.</span><span class="sxs-lookup"><span data-stu-id="889ab-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="889ab-109">См. также</span><span class="sxs-lookup"><span data-stu-id="889ab-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
