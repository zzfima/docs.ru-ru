---
ms.openlocfilehash: 77e04333ed2b9a5ca8b900c1355fb5b12957772d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774444"
---
### <a name="machinekeyencode-and-machinekeydecode-methods-are-now-obsolete"></a>Методы MachineKey.Encode и MachineKey.Decode устарели

|   |   |
|---|---|
|Подробные сведения|В настоящее время эти методы считаются устаревшими. При компиляции кода, который вызывает эти методы, создается предупреждение компилятора.|
|Предложение|Взамен рекомендуется использовать <xref:System.Web.Security.MachineKey.Protect(System.Byte[],System.String[])> и <xref:System.Web.Security.MachineKey.Unprotect(System.Byte[],System.String[])>. Кроме того, можно подавить предупреждения сборки или избежать их вывода с помощью более старой версии компилятора. Интерфейсы API по-прежнему поддерживаются.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Web.Security.MachineKey.Encode(System.Byte[],System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li><li><xref:System.Web.Security.MachineKey.Decode(System.String,System.Web.Security.MachineKeyProtection)?displayProperty=nameWithType></li></ul>|
