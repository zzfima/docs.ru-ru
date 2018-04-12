---
title: Файл уже открыт
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3305831e840510e3f0b5bcb8bf847e39ea3ee4ba
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="file-already-open"></a><span data-ttu-id="eb779-102">Файл уже открыт</span><span class="sxs-lookup"><span data-stu-id="eb779-102">File already open</span></span>
<span data-ttu-id="eb779-103">В некоторых случаях файл необходимо закрыть перед другим `FileOpen` или другую операцию.</span><span class="sxs-lookup"><span data-stu-id="eb779-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="eb779-104">Некоторые из возможных причин этой ошибки:</span><span class="sxs-lookup"><span data-stu-id="eb779-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="eb779-105">Режим последовательного вывода `FileOpen` операция была выполнена для файла, который уже открыт</span><span class="sxs-lookup"><span data-stu-id="eb779-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="eb779-106">Оператор ссылается на открытый файл.</span><span class="sxs-lookup"><span data-stu-id="eb779-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eb779-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="eb779-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="eb779-108">Закройте файл перед выполнением инструкции.</span><span class="sxs-lookup"><span data-stu-id="eb779-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb779-109">См. также</span><span class="sxs-lookup"><span data-stu-id="eb779-109">See Also</span></span>  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
