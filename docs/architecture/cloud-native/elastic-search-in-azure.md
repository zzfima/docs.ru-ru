---
title: Упругий поиск в облачных приложениях
description: Узнайте о добавлении возможностей Elastic Search в облачные приложения.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 1bce255b6315006b11e0b6ac77040300f67ed984
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141293"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>Elasticsearch в облачно-родном приложении

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Elasticsearch — это распределенная система поиска и аналитики, которая позволяет создавать сложные возможности поиска в различных типах данных. Это с открытым исходным кодом и широко популярны. Рассмотрим, как следующие компании интегрируют Elasticsearch в свое приложение:

- [Википедия](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) для полного текста и инкрементного (поиск по мере ввода) поиска.
- [GitHub](https://www.elastic.co/customers/github) для индексирования и разоблачения более 8 миллионов хранилищ кода.  
- [Докер](https://www.elastic.co/customers/docker) для того, чтобы сделать его контейнер библиотеки обнаружить.

Elasticsearch построен на вершине полнотекстовый поисковой системы [Apache Lucene.](https://lucene.apache.org/core/) Lucene обеспечивает высокопроизводительную индексацию и запросы документов. Он индексирует данные с перевернутой схемой индексирования – вместо отображения страниц на ключевые слова, он отображает ключевые слова на страницах так же, как глоссарий в конце книги. Lucene обладает мощными возможностями синтаксиса запросов и может задавлять данные по следующим данным:

- Срок (полное слово)
- Префикс (начинается со слова)
- Wildcard (с\*использованием фильтров "или "?"
- Фраза (последовательность текста в документе)
- Значение Boolean (сложный поиск, объединяющий запросы)

В то время как Lucene предоставляет низкоуровневую сантехнику для поиска, Elasticsearch предоставляет сервер, который находится на вершине Lucene. Elasticsearch добавляет функциональность более высокого уровня для упрощения работы Lucene, включая RESTful API для доступа к функциональности индексирования и поиска Lucene. Он также обеспечивает распределенную инфраструктуру, способную к массовой масштабируемости, толерантности к ошибкам и высокой доступности.

Для более крупных облачных приложений со сложными требованиями к поиску Elasticsearch доступен в качестве управляемого сервиса в Azure. В Microsoft Azure Marketplace есть преднастроенные шаблоны, которые разработчики могут использовать для развертывания кластера Elasticsearch в Azure.

В Microsoft Azure Marketplace разработчики могут использовать предварительно настроенные шаблоны, созданные для быстрого развертывания кластера Elasticsearch в Azure. Используя предложение, управляемое Azure, можно развернуть до 50 узлов данных, 20 координационных узлов и три выделенных узла.

## <a name="summary"></a>Сводка

В этой главе представлен подробный взгляд на данные в облачных системах. Мы начали с противопоставления хранения данных в монолитных приложениях с шаблонами хранения данных в облачных системах. Мы рассмотрели шаблоны данных, реализованные в облачных системах, включая запросы о перекрестном обслуживании, распределенные транзакции и шаблоны работы с высокообъемными системами. Мы сравнили с данными NoS'L данные. Мы рассмотрели варианты хранения данных, доступные в Azure, которые включают как ориентированные на Microsoft, так и варианты с открытым исходным кодом. Наконец, мы обсудили кэширование и Elasticsearch в облачном приложении.

### <a name="references"></a>Ссылки

- [Шаблон CQRS](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [Шаблон поиска событий](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)

- [RDBMSvs vs. Базы данных НоСЗЛ: Обзор](https://maxivak.com/rdbms-vs-nosql-databases/)

- [Почему в теореме CAP не толерантна раздел RDBMS и почему она доступна?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [Материализованный вид](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [Все, что вам действительно нужно знать о базах данных с открытым исходным кодом](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [Шаблон компенсирующих транзакций](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Шаблон саги](https://microservices.io/patterns/data/saga.html)

- [Сага Шаблоны (ru) Как осуществлять бизнес-операции с помощью микрослужб](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [Шаблон компенсирующих транзакций](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Получение за 9-Ball: Космос DB Последовательность Уровни Разъяснения](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [Изучение различных типов баз данных НоСЗЛ Часть II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [По базам данных RDBMS, NoS'L и NewS'L. Интервью с Джоном Райаном](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [СЗЛ vs НоСЗЛ vs НьюСЗЛ: Полное сравнение](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [DASH: Четыре свойства базы данных Kubernetes-Native](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [ТараканDB](https://www.cockroachlabs.com/)

- [TiDB](https://pingcap.com/en/)

- [YugabyteDB](https://www.yugabyte.com/)

- [Витесс](https://vitess.io/)

- [Elasticsearch: The Definitive Guide (Elasticsearch: полное руководство)](http://shop.oreilly.com/product/0636920028505.do)
  
- [Введение в Апач Лусене](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[Предыдущий](azure-caching.md)
>[Следующий](resiliency.md) <!-- Next Chapter -->
