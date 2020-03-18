---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920659"
---

<span data-ttu-id="a886d-101">При установке пакета .NET Core может появиться примерно такое сообщение об ошибке: `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span><span class="sxs-lookup"><span data-stu-id="a886d-101">While installing the .NET Core package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="a886d-102">В целом, эта ошибка означает, что веб-канал пакета для .NET Core сейчас обновляется до новой версии пакета и следует повторить попытку позже.</span><span class="sxs-lookup"><span data-stu-id="a886d-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="a886d-103">Во время обновления канал пакета остается недоступным не более чем в течение 30-х минут.</span><span class="sxs-lookup"><span data-stu-id="a886d-103">During an upgrade, the package feed should not be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="a886d-104">Если вы продолжаете получать эту ошибку через 30 минут, отправьте заявку о проблеме на адрес <https://github.com/dotnet/core/issues>.</span><span class="sxs-lookup"><span data-stu-id="a886d-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>
