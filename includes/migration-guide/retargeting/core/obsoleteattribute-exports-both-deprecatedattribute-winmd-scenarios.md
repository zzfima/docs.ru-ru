---
ms.openlocfilehash: e8c48c4b1031813ce62f576e5bf1f94c082dfe4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774432"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a>Атрибут ObsoleteAttribute экспортируется как ObsoleteAttribute и DeprecatedAttribute в сценариях WinMD

|   |   |
|---|---|
|Подробные сведения|При создании библиотеки метаданных Windows (WINMD-файл) атрибут <xref:System.ObsoleteAttribute?displayProperty=name> экспортируется как <xref:System.ObsoleteAttribute?displayProperty=name> и [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).|
|Предложение|При перекомпиляции существующего исходного кода, использующего атрибут <xref:System.ObsoleteAttribute?displayProperty=name>, могут выдаваться предупреждения при использовании кода из C++/CX или JavaScript. Не рекомендуется применять атрибуты <xref:System.ObsoleteAttribute?displayProperty=name> и [ Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) в коде в управляемых сборках. Это может привести к предупреждениям сборки.|
|Область|Пограничный случай|
|Версия|4.5.1|
|Тип|Изменение целевой платформы|
