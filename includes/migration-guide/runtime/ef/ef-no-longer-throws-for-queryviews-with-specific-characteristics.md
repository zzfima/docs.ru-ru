---
ms.openlocfilehash: 705e1a22b8a5791c1103dd374a8bab19356cadfb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236657"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>EF более не создает исключения для представлений QueryView с определенными характеристиками

|   |   |
|---|---|
|Подробные сведения|Entity Framework больше не создает исключение <xref:System.StackOverflowException?displayProperty=name>, если приложение выполняет запрос, включающий представление QueryView со свойством навигации 0..1, которое пытается включить связанные объекты в запрос. Например, это могло быть сделано путем вызова <code>.Include(e =&gt; e.RelatedNavProp)</code>.|
|Предложение|Это изменение влияет только на код, использующий представления QueryView с отношениями 1-0..1 при выполнении запросов, вызывающих метод .Include. Эта функция повышает надежность и должна быть прозрачна почти для всех приложений. Тем не менее, если она вызывает непредвиденное поведение, ее можно отключить, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Версия|4.5.2|
|Тип|Среда выполнения|
