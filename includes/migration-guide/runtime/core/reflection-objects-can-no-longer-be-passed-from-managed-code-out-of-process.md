---
ms.openlocfilehash: d00f86c492a7d32344b1067a48c8e53aa2a43426
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858444"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM

|   |   |
|---|---|
|Подробные сведения|Объекты отражения больше невозможно передавать из управляемого кода во внепроцессные клиенты DCOM. Затронуты следующие типы:<ul><li><xref:System.Reflection.Assembly?displayProperty=name></li><li><xref:System.Reflection.MemberInfo?displayProperty=name> (и его производные типы, включая <xref:System.Reflection.FieldInfo?displayProperty=name>, <xref:System.Reflection.MethodInfo?displayProperty=name>, <xref:System.Type?displayProperty=name> и <xref:System.Reflection.TypeInfo?displayProperty=name>)</li><li><xref:System.Reflection.MethodBody?displayProperty=name></li><li><xref:System.Reflection.Module?displayProperty=name></li><li><xref:System.Reflection.ParameterInfo?displayProperty=name>.</li></ul>Вызовы <code>IMarshal</code> объекта возвращают <code>E_NOINTERFACE</code>.|
|Предложение|Обновите код маршалинга для работы с объектами без отражения|
|Область|Дополнительный номер|
|Версия|4.6|
|Тип|Среда выполнения|

