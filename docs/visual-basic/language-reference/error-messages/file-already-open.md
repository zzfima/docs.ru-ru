---
title: Файл уже открыт
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 8ec878e04b0128c997c5be51d2c714d55abcde8c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665118"
---
# <a name="file-already-open"></a><span data-ttu-id="e7581-102">Файл уже открыт</span><span class="sxs-lookup"><span data-stu-id="e7581-102">File already open</span></span>
<span data-ttu-id="e7581-103">Иногда файл должен быть закрыт перед другим `FileOpen` или другую операцию.</span><span class="sxs-lookup"><span data-stu-id="e7581-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="e7581-104">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="e7581-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="e7581-105">Режим последовательного вывода `FileOpen` операция была выполнена для файла, который уже открыт</span><span class="sxs-lookup"><span data-stu-id="e7581-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="e7581-106">Оператор ссылается на открытый файл.</span><span class="sxs-lookup"><span data-stu-id="e7581-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e7581-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e7581-107">To correct this error</span></span>  
  
1. <span data-ttu-id="e7581-108">Закройте файл перед выполнением инструкции.</span><span class="sxs-lookup"><span data-stu-id="e7581-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7581-109">См. также</span><span class="sxs-lookup"><span data-stu-id="e7581-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
