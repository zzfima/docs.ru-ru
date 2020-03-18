---
ms.openlocfilehash: 38c774417fc94fa080bf2b82c04d575e9068cdcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858444"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM

|   |   |
|---|---|
|Подробнее|Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM. Затронуты следующие типы:<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name> (и его производные типы, включая <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name> и <xref:System.Reflection.TypeInfo?displayProperty=name>)</li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>Вызовы <code>IMarshal</code> объекта возвращают <code>E_NOINTERFACE</code>.|
|Предложение|Обновите код маршалинга для работы с объектами без отражения|
|Область|Дополнительный номер|
|Version|4.6|
|Type|Параметры выполнения|
