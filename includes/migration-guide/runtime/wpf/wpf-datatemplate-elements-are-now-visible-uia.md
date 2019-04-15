---
ms.openlocfilehash: 51691ced3f05201f784ccdeffbc130e34748b7c1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235567"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a>Элементы WPF DataTemplate теперь отображаются в UIA

|   |   |
|---|---|
|Подробные сведения|Ранее элементы <xref:System.Windows.DataTemplate?displayProperty=name> не отображались в службе автоматизации пользовательского интерфейса. Начиная с версии 4.5, служба автоматизации пользовательского интерфейса будет обнаруживать эти элементы. Это полезно во многих случаях, но может нарушить выполнение тестов, зависящих от деревьев UIA, не содержащих элементы <xref:System.Windows.DataTemplate?displayProperty=name>.|
|Предложение|Тесты службы автоматизации пользовательского интерфейса для этого приложения может потребоваться обновить с учетом того, что теперь дерево UIA содержит ранее невидимые элементы <xref:System.Windows.DataTemplate?displayProperty=name>. Например, тесты, которые ожидают, что некоторые элементы находятся рядом друг с другом, теперь могут ожидать, что между ними располагаются ранее невидимые элементы UIA. Или может потребоваться обновить новыми значениями тесты, которые зависят от определенных количеств или индексов для UIA элементов.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Windows.DataTemplate.%23ctor?displayProperty=nameWithType></li><li><xref:System.Windows.DataTemplate.%23ctor(System.Object)?displayProperty=nameWithType></li></ul>|
