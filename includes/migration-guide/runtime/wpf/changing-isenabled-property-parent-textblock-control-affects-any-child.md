---
ms.openlocfilehash: 735278848cb7399e414a128afc650a0a1f882337
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857568"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>Изменение свойства IsEnabled для родительского объекта элемента управления TextBlock влияет на любые дочерние элементы управления

|   |   |
|---|---|
|Подробнее|Начиная с версии .NET Framework 4.6.2, изменение свойства <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> родительского объекта элемента управления <xref:System.Windows.Controls.TextBlock?displayProperty=name> влияет на любые дочерние элементы управления (например, гиперссылки и кнопки) элемента <xref:System.Windows.Controls.TextBlock?displayProperty=name>. В .NET Framework 4.6.1 и более ранних версий элементы управления внутри элемента <xref:System.Windows.Controls.TextBlock?displayProperty=name> не всегда отражали состояние свойства <xref:System.Windows.UIElement.IsEnabled?displayProperty=name> родительского объекта <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Предложение|Нет. Это изменение соответствует ожидаемому поведению для элементов управления, содержащихся внутри элемента управления <xref:System.Windows.Controls.TextBlock?displayProperty=name>.|
|Область|Дополнительный номер|
|Version|4.6.2|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|
