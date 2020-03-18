---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67856959"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Улучшенные подсказки клавиш в WPF

|   |   |
|---|---|
|Подробнее|Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word. WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом. Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.|
|Предложение|Недоступно|
|Область|Пограничный случай|
|Version|4.7.2|
|Type|Параметры выполнения|
