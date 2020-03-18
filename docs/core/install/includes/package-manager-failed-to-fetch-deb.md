---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920659"
---

При установке пакета .NET Core может появиться примерно такое сообщение об ошибке: `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`. В целом, эта ошибка означает, что веб-канал пакета для .NET Core сейчас обновляется до новой версии пакета и следует повторить попытку позже. Во время обновления канал пакета остается недоступным не более чем в течение 30-х минут. Если вы продолжаете получать эту ошибку через 30 минут, отправьте заявку о проблеме на адрес <https://github.com/dotnet/core/issues>.
