---
ms.openlocfilehash: 3b7309347c643d89a28331c6ef3cac36085a969a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234282"
---
### <a name="wpf-windows-are-rendered-without-clipping-when-extending-outside-a-single-monitor"></a>Окна WPF отображаются без обрезки, если изображение выходит за пределы одного монитора

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.6 на компьютере под управлением Windows 8 и более поздних версий все содержимое окна выводится без обрезки, если изображение выходит за пределы одного экрана при использовании нескольких мониторов. Это отличается от предыдущих версий .NET Framework, где окна WPF обрезались, если выходили за пределы одного экрана.|
|Предложение|Это поведение (отсутствие или наличие обрезки) можно задать явным образом с помощью элемента <code>&lt;EnableMultiMonitorDisplayClipping&gt;</code> в <code>&lt;appSettings&gt;</code> в файле конфигурации приложения или задав свойство <code>EnableMultiMonitorDisplayClipping</code> при запуске приложения.|
|Область|Дополнительный номер|
|Версия|4.6|
|Тип|Среда выполнения|
