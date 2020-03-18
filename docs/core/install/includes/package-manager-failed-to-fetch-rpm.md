---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920739"
---

<span data-ttu-id="e2b92-101">При установке пакета .NET Core может появиться примерно такое сообщение об ошибке: `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span><span class="sxs-lookup"><span data-stu-id="e2b92-101">While installing the .NET Core package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="e2b92-102">В целом, эта ошибка означает, что веб-канал пакета для .NET Core сейчас обновляется до новой версии пакета и следует повторить попытку позже.</span><span class="sxs-lookup"><span data-stu-id="e2b92-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="e2b92-103">При обновлении канал пакета недоступен не более двух часов.</span><span class="sxs-lookup"><span data-stu-id="e2b92-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="e2b92-104">Если эта ошибка сохраняется более двух часов, сообщите о проблеме по адресу <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="e2b92-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
