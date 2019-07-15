---
ms.openlocfilehash: 9ad283af76085c228bedceb6db723a1d18b10210
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67804407"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a>Имена событий в трассировке событий Windows не должны отличаться друг от друга только суффиксами "Start" или "Stop"

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.6 и 4.6.1 среда выполнения вызывает исключение <xref:System.ArgumentException> в случае, когда имена двух событий в трассировке событий Windows отличаются только суффиксами &quot;Start&quot; или &quot;Stop&quot; (например, одно событие с именем <code>LogUser</code>, а другое с именем <code>LogUserStart</code>). В этом случае среда выполнения не может определить источник событий и, соответственно, сделать запись в журнале.|
|Предложение|Чтобы не возникло исключение, убедитесь, что имена событий не отличаются только суффиксами &quot;Start&quot; или &quot;Stop&quot;. Это требование снято начиная с версии .NET Framework 4.6.2. Среда выполнения может устранить неоднозначность имен событий, которые отличаются только суффиксами &quot;Start&quot; и &quot;Stop&quot;.|
|Область|Пограничный случай|
|Версия|4.6|
|Тип|Изменение целевой платформы|

