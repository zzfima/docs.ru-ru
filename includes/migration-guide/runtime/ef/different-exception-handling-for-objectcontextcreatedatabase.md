---
ms.openlocfilehash: 33ad1c044001e0a8d09708cc7a1f06e05cb307de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804930"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>Исключения обрабатываются по-разному для методов ObjectContext.CreateDatabase и DbProviderServices.CreateDatabase

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5, если происходит сбой создания базы данных, методы <code>CreateDatabase</code> будут пытаться удалить пустую базу данных. Если эта операция выполняется успешно, будет распространяться исходное исключение <xref:System.Data.SqlClient.SqlException?displayProperty=name> (вместо <xref:System.InvalidOperationException?displayProperty=name>, которое всегда создавалось в .NET Framework 4.0).|
|Предложение|При перехвате <xref:System.InvalidOperationException?displayProperty=name> во время выполнения <xref:System.Data.Objects.ObjectContext.CreateDatabase> или <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)> теперь также должны обрабатываться исключения SQLException.|
|Область|Дополнительный номер|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
