---
ms.openlocfilehash: 9500907c6a1ba5b27008dcad4c9b47aef9092106
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802492"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>В локализованных сборках для RibbonGroup устанавливается прозрачный фон

|   |   |
|---|---|
|Подробные сведения|Фон <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> в локализованных сборках всегда закрашивается с использованием прозрачной кисти, что ухудшает восприятие пользовательского интерфейса. Решение приведено в исправлении WPF в .NET Framework 4.7, где были обновлены локализованные ресурсы для <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name>, благодаря чему гарантируется выбор правильной кисти.|
|Предложение|Выполните обновление до .NET Framework 4.7.|
|Область|Пограничный случай|
|Версия|4.6.2|
|Тип|Среда выполнения|

