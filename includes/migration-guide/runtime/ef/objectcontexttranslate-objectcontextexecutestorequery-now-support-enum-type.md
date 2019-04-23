---
ms.openlocfilehash: 1d2d6133683360b97569e49402e7c8c4d182b65d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804898"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>ObjectContext.Translate и ObjectContext.ExecuteStoreQuery теперь поддерживают тип перечисления

|   |   |
|---|---|
|Подробные сведения|В .NET Framework 4.0 универсальный параметр <code>T</code> методов <code>ObjectContext.Translate</code> и <code>ObjectContext.ExecuteStoreQuery</code> не мог иметь тип перечисления. Теперь этот сценарий поддерживается.|
|Предложение|Если метод Translate или ExecuteStoreQuery вызывался для типа перечисления в .NET Framework 4.0, возвращалось значение "0". Если такое поведение было желательным, вызовы следовало заменять константой 0 (или его эквивалентом перечисления).|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
