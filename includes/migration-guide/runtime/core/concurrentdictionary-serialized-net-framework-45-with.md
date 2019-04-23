---
ms.openlocfilehash: f9d7b8d22818245b96cafffe3732bdfe82ff69d8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804951"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>Объект ConcurrentDictionary, сериализованный в .NET Framework 4.5 с помощью NetDataContractSerializer, нельзя десериализовать в .NET Framework 4.5.1 или 4.5.2

|   |   |
|---|---|
|Подробные сведения|Из-за внутренних изменений типа объекты <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, сериализованные в .NET Framework 4.5 с помощью <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>, не могут быть десериализованы в .NET Framework 4.5.1 или .NET Framework 4.5.2. Обратите внимание, что сериализация в .NET Framework 4.5.x с последующей десериализацией в .NET Framework 4.5 будет работать нормально. Аналогичным образом, сериализация в версиях 4.x работает в .NET Framework 4.6. Сериализация и десериализация в одной версии платформы .NET Framework не затрагивается.|
|Предложение|Если требуется выполнить сериализацию и десериализацию объектов <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> между версиями .NET Framework 4.5 и .NET Framework 4.5.1/4.5.2, следует использовать альтернативный сериализатор, например <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> или <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name>, вместо <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>. Кроме того, поскольку эта проблема была устранена в .NET Framework 4.6, она может быть решена путем обновления до этой версии платформы .NET Framework.|
|Область|Дополнительный номер|
|Версия|4.5.1|
|Тип|Среда выполнения|
