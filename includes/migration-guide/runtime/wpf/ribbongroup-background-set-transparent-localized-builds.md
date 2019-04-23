---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59236092"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>В локализованных сборках для RibbonGroup устанавливается прозрачный фон

|   |   |
|---|---|
|Подробные сведения|Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса. Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, благодаря чему гарантируется выбор правильной кисти.|
|Предложение|Выполните обновление до .NET Framework 4.7.|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Среда выполнения|
