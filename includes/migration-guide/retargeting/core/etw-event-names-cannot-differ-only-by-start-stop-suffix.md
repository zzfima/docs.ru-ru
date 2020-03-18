---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804407"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>Имена событий в трассировке событий Windows не должны отличаться друг от друга только суффиксами "Start" или "Stop"

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.6 и 4.6.1 среда выполнения вызывает исключение <xref:System.ArgumentException> в случае, когда имена двух событий в трассировке событий Windows отличаются только суффиксами &quot;Start&quot; или &quot;Stop&quot; (например, одно событие с именем <code>LogUser</code>, а другое с именем <code>LogUserStart</code>). В этом случае среда выполнения не может определить источник событий и, соответственно, сделать запись в журнале.|
|Предложение|Чтобы не возникло исключение, убедитесь, что имена событий не отличаются только суффиксами &quot;Start&quot; или &quot;Stop&quot;. Это требование снято начиная с версии .NET Framework 4.6.2. Среда выполнения может устранить неоднозначность имен событий, которые отличаются только суффиксами &quot;Start&quot; и &quot;Stop&quot;.|
|Область|Пограничный случай|
|Version|4.6|
|Type|Изменение целевой платформы|
