---
ms.openlocfilehash: b23f06ec5b27fbd7976a4b62ba6105c607eaee39
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236701"
---
### <a name="some-net-apis-cause-first-chance-handled-entrypointnotfoundexceptions"></a>Некоторые интерфейсы API .NET создают первый экземпляр (обрабатываемый) EntryPointNotFoundExceptions

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.5 несколько методов .NET начали создавать первый экземпляр <xref:System.EntryPointNotFoundException?displayProperty=name>. Эти исключения обрабатывались в .NET Framework, но могли нарушать работу службы автоматизации тестирования, которая не ожидала первых экземпляров исключений. Те же интерфейсы API препятствуют работе некоторых сценариев ApiVerifier, если включен тест HighVersionLie.|
|Предложение|Этой ошибки можно избежать путем обновления до .NET Framework 4.5.1. Кроме того, службу автоматизации тестирования можно обновить, чтобы она не прерывала свое выполнение при создании первого экземпляра <xref:System.EntryPointNotFoundException?displayProperty=name>.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Diagnostics.Debug.Assert(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Debug.Assert(System.Boolean,System.String,System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.%23ctor(System.Type)?displayProperty=nameWithType></li></ul>|
