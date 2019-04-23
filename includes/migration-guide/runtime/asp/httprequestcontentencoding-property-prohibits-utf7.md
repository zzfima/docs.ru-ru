---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804917"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>Свойство HttpRequest.ContentEncoding запрещает кодировку UTF7

|   |   |
|---|---|
|Подробные сведения|Начиная с .NET Framework 4.5 кодировка UTF-7 запрещена в теле <xref:System.Web.HttpRequest?displayProperty=name>. Данные для приложений, которые зависят от поступающих данных UTF-7, в некоторых случаях декодируются неверно.|
|Предложение|В идеальном случае приложения необходимо обновить, чтобы они не использовали кодировку UTF-7 в <xref:System.Web.HttpRequest?displayProperty=name>. Кроме того, устаревшее поведение можно восстановить с помощью атрибута <code>aspnet:AllowUtf7RequestContentEncoding</code> элемента [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).|
|Область|Пограничный случай|
|Версия|4.5|
|Тип|Среда выполнения|
|Затронутые API|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
