---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804868"
---
### <a name="keytips-behavior-improved-in-wpf"></a>Улучшенные подсказки клавиш в WPF

|   |   |
|---|---|
|Подробные сведения|Поведение подсказок клавиш было изменено и теперь совпадает с поведением в проводнике и Microsoft Word. WPF проверяет, включено ли состояние подсказки клавиш в случае, если нажата <xref:System.Windows.Input.KeyEventArgs.SystemKey> (в частности, <xref:System.Windows.Input.Key> или <xref:System.Windows.Input.Key.F11>), и обрабатывает клавиши подсказок соответствующим образом. Подсказки клавиш теперь закрывают меню, даже если оно открыто с помощью мыши.|
|Предложение|Н/Д|
|Область|Пограничный случай|
|Версия|4.7.2|
|Тип|Среда выполнения|
