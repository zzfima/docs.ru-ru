---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802492"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>В локализованных сборках для RibbonGroup устанавливается прозрачный фон

|   |   |
|---|---|
|Подробнее|Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса. Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, благодаря чему гарантируется выбор правильной кисти.|
|Предложение|Выполните обновление до .NET Framework 4.7.|
|Область|Пограничный случай|
|Version|4.6.2|
|Type|Параметры выполнения|
