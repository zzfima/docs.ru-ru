---
ms.openlocfilehash: d7cf32eb369e2607ee540d7188cc680b9506c261
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760759"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Улучшенные подсказки клавиш в WPF

|   |   |
|---|---|
|Подробные сведения|Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word. WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом. Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.|
|Предложение|Н/Д|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Среда выполнения|

