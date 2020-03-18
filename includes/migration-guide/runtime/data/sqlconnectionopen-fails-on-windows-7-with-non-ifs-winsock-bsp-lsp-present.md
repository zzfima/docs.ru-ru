---
ms.openlocfilehash: 65d9edc1e7377a86f8185ebf28bb5bee3a3f887d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803151"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>SqlConnection.Open завершается ошибкой в Windows 7 при наличии базовых поставщиков услуг или многоуровневых поставщиков услуг Winsock, не относящихся к IFS

|   |   |
|---|---|
|Подробнее|<xref:System.Data.SqlClient.SqlConnection.Open> и <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> завершаются сбоем в .NET Framework 4.5 в Windows 7 при наличии на компьютере базовых поставщиков услуг или многоуровневых поставщиков услуг Winsock, не относящихся к IFS. Чтобы определить, установлен ли базовый или многоуровневый поставщик услуг, не относящийся к IFS, выполните команду <code>netsh WinSock Show Catalog</code> и проверьте все возвращаемые ей элементы <code>Winsock Catalog Provider Entry</code>. Если в качестве значения флагов службы задано <code>0x20000</code> бит, поставщик использует маркеры IFS и будет работать правильно. Если флаг <code>0x20000</code> бит снят (значение не задано), это поставщик BSP или LSP, не относящийся к IFS.|
|Предложение|Это ошибка исправлена в .NET Framework 4.5.2, поэтому ее можно избежать путем обновления .NET Framework. Кроме того, ее можно избежать, удалив все установленные поставщики LSP Winsock, не относящиеся к IFS.|
|Область|Дополнительный номер|
|Version|4,5|
|Type|Параметры выполнения|
|Затронутые API|<ul><li><xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
