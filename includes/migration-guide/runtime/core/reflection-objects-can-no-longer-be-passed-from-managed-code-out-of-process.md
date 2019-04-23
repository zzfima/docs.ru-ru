---
ms.openlocfilehash: 38c774417fc94fa080bf2b82c04d575e9068cdcb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59234270"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM

|   |   |
|---|---|
|Подробные сведения|Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM. Затронуты следующие типы:<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name> (и его производные типы, включая <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name> и <xref:System.Reflection.TypeInfo?displayProperty=name>)</li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>Вызовы <code>IMarshal</code> объекта возвращают <code>E_NOINTERFACE</code>.|
|Предложение|Обновите код маршалинга для работы с объектами без отражения|
|Область|Дополнительный номер|
|Версия|4.6|
|Тип|Среда выполнения|
