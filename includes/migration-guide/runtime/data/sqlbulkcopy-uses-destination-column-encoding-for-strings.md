---
ms.openlocfilehash: fa09831ac47a59535ff73c8c8680c2642c3248c9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235519"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a>SqlBulkCopy использует кодировку целевого столбца для строк

|   |   |
|---|---|
|Подробные сведения|При вставке данных в столбец <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=name> использует кодировку целевого столбца, а не кодировку по умолчанию для типов <code>VARCHAR</code> и <code>CHAR</code>. Это изменение исключает возможность повреждения данных, вызванного использованием кодировки по умолчанию, если в целевом столбце не используется кодировка по умолчанию. В редких случаях существующее приложение может создавать исключение SqlException, если при изменении кодировки создаются слишком большие для целевого столбца данные.|
|Предложение|Учитывайте, что <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=name> больше не будет повреждать данные из-за различий в кодировке. Если размер копируемых строк близок к установленному для целевого столбца ограничению, может потребоваться предварительное кодирование данных (с целью копирования для проверки того, что они поместятся в целевом столбце) или перехват исключений <xref:System.Data.SqlClient.SqlException?displayProperty=name>.|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)?displayProperty=nameWithType></li></ul>|
