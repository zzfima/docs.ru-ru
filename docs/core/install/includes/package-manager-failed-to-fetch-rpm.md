---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920739"
---

При установке пакета .NET Core может появиться примерно такое сообщение об ошибке: `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`. В целом, эта ошибка означает, что веб-канал пакета для .NET Core сейчас обновляется до новой версии пакета и следует повторить попытку позже. При обновлении канал пакета недоступен не более двух часов. Если эта ошибка сохраняется более двух часов, сообщите о проблеме по адресу <https://github.com/dotnet/core/issues>.
