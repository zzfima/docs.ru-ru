---
ms.openlocfilehash: e7a5a95a5d13f3396d396ad0d74a19a0efa3a967
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235531"
---
### <a name="sqlvariant-data-uses-sqlvariant-collation-rather-than-database-collation"></a>В данных Sql_variant используется сортировка sql_variant, а не сортировка базы данных

|   |   |
|---|---|
|Подробные сведения|В данных <code>sql_variant</code> используется сортировка <code>sql_variant</code>, а не сортировка базы данных.|
|Предложение|Это изменение предотвращает возможное повреждение данных, если сортировка базы данных отличается от сортировки <code>sql_variant</code>. В приложениях, в которых предполагается, что данные будут повреждены, могут возникать сбои.|
|Область|Прозрачный|
|Версия|4.5|
|Тип|Среда выполнения|
