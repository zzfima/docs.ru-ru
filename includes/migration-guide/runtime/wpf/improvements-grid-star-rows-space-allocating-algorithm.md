---
ms.openlocfilehash: 770e303ab261b97efb49a3e0865a015d8de33247
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802694"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Усовершенствования алгоритма выделения пространства для строк со звездами в сетке

|   |   |
|---|---|
|Подробные сведения|Исправлена ошибка в [алгоритме выделения размеров для ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md) в <xref:System.Windows.Controls.Grid>, представленном в .NET Framework 4.7.  В некоторых случаях, например в сетке с <code>Height=&quot;Auto&quot;</code>, которая содержит пустые строки, строки были расположены в неправильном положении, возможно, даже за пределами сетки.|
|Предложение|Чтобы эти изменения можно было использовать в приложении, оно должно быть запущено на платформе .NET Framework 4.8 или более поздней версии.|
|Область|Значительно|
|Версия|4.8|
|Тип|Среда выполнения|

