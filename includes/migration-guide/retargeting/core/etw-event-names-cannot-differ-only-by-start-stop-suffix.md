---
ms.openlocfilehash: 71c81cf188fa4c2300661f10eb87e7ae00e031f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804926"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>Имена событий в трассировке событий Windows не должны отличаться друг от друга только суффиксами "Start" или "Stop"

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.6 и 4.6.1 среда выполнения вызывает исключение <xref:System.ArgumentException> в случае, когда имена двух событий в трассировке событий Windows отличаются только суффиксами &quot;Start&quot; или &quot;Stop&quot; (например, одно событие с именем <code>LogUser</code>, а другое с именем <code>LogUserStart</code>). В этом случае среда выполнения не может определить источник событий и, соответственно, сделать запись в журнале.|
|Предложение|Чтобы не возникло исключение, убедитесь, что имена событий не отличаются только суффиксами &quot;Start&quot; или &quot;Stop&quot;. Это требование снято начиная с версии .NET Framework 4.6.2. Среда выполнения может устранить неоднозначность имен событий, которые отличаются только суффиксами &quot;Start&quot; и &quot;Stop&quot;.|
|Область|Пограничный случай|
|Версия|4.6|
|Тип|Изменение целевой платформы|
