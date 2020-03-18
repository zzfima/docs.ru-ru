---
ms.openlocfilehash: 705e1a22b8a5791c1103dd374a8bab19356cadfb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803273"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a>EF более не создает исключения для представлений QueryView с определенными характеристиками

|   |   |
|---|---|
|Подробнее|Entity Framework больше не создает исключение <xref:System.StackOverflowException?displayProperty=name>, если приложение выполняет запрос, включающий представление QueryView со свойством навигации 0..1, которое пытается включить связанные объекты в запрос. Например, это могло быть сделано путем вызова <code>.Include(e =&gt; e.RelatedNavProp)</code>.|
|Предложение|Это изменение влияет только на код, использующий представления QueryView с отношениями 1-0..1 при выполнении запросов, вызывающих метод .Include. Эта функция повышает надежность и должна быть прозрачна почти для всех приложений. Тем не менее, если она вызывает непредвиденное поведение, ее можно отключить, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Version|4.5.2|
|Type|Параметры выполнения|
