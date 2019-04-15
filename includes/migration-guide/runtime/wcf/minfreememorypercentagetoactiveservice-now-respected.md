---
ms.openlocfilehash: fa472b3a142f55f0cbdd83eabbbb00bddd9786d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235886"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a>Параметр MinFreeMemoryPercentageToActiveService теперь учитывается

|   |   |
|---|---|
|Подробные сведения|Этот параметр задает минимальный объем памяти, который должен быть доступен на сервере перед активацией службы WCF. Он предназначен для предотвращения исключений <xref:System.OutOfMemoryException?displayProperty=name>. В .NET Framework 4.5 этот параметр не оказывал никакого влияния. В .NET Framework 4.5.1 этот параметр уже используется.|
|Предложение|Исключение возникает, если объем свободной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации. Некоторые службы WCF, которые успешно запускались и выполнялись в условиях ограниченной памяти, теперь могут завершаться ошибкой.|
|Область|Дополнительный номер|
|Версия|4.5.1|
|Тип|Среда выполнения|
