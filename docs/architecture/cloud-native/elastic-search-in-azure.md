---
title: Elasticsearch в собственных приложениях в облаке
description: Узнайте о добавлении возможностей эластичного поиска в собственные облачные приложения.
author: robvet
ms.date: 01/22/2020
ms.openlocfilehash: 6ea237eddc89a8c6843d6b34b05b1b71515a99b6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76795041"
---
# <a name="elasticsearch-in-a-cloud-native-app"></a>Elasticsearch в собственном облачном приложении

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Elasticsearch — это распределенная система поиска и аналитики, которая обеспечивает сложные возможности поиска по различным типам данных. Это открытый исходный код и широко распространенный. Рассмотрим, как следующие компании интегрируют Elasticsearch в свои приложения:

- [Википедии](https://blog.wikimedia.org/2014/01/06/wikimedia-moving-to-elasticsearch/) для полнотекстового и добавочного поиска (Поиск по мере ввода).
- [GitHub](https://www.elastic.co/customers/github) для индексирования и предоставления более 8 000 000 репозиториев кода.  
- [DOCKER](https://www.elastic.co/customers/docker) , чтобы сделать его библиотекой контейнеров обнаруживаемой.

Elasticsearch построен на базе механизма полнотекстового поиска [Apache Lucene](https://lucene.apache.org/core/) . Lucene обеспечивает высокую производительность индексирования документов и запросов. Он индексирует данные с инверсной схемой индексирования, вместо того чтобы сопоставлять страницы с ключевыми словами, она сопоставляет ключевые слова со страницами так же, как Глоссарий в конце книги. Lucene обладает мощными возможностями синтаксиса запросов и может запрашивать данные с помощью следующих средств:

- Term (полное слово) 
- Префикс (начинается с слова)
- Подстановочный знак (с помощью фильтров "\*" или "?")
- Фраза (последовательность текста в документе)
- Логическое значение (сложные поиски, объединяющие запросы)

Хотя Lucene предоставляет низкоуровневые коммуникации для поиска, Elasticsearch предоставляет сервер, расположенный на основе Lucene. Elasticsearch добавляет функции более высокого уровня для упрощения работы с Lucene, включая API RESTFUL для доступа к функциям индексирования и поиска Lucene. Она также предоставляет распределенную инфраструктуру с широкими возможностями масштабирования, отказоустойчивости и высокой доступности.

Для более крупных облачных приложений с комплексными требованиями поиска Elasticsearch доступен в качестве управляемой службы в Azure. Microsoft Azure Marketplace содержит предварительно настроенные шаблоны, которые разработчики могут использовать для развертывания кластера Elasticsearch в Azure.

С Microsoft Azure Marketplace разработчики могут использовать предварительно настроенные шаблоны, созданные для быстрого развертывания кластера Elasticsearch в Azure. С помощью предложения, управляемого Azure, можно развернуть до 50 узлов данных, 20 координирующих узлов и трех выделенных главных узлов.

## <a name="summary"></a>Сводка

В этой главе представлен подробный обзор данных в собственных облачных системах. Мы начали с того, чтобы сравнить объем хранилища данных в монолитных приложениях с шаблонами хранения данных в собственных системах в облаке. Мы рассматривали шаблоны данных, реализованные в собственных системах, включая запросы между службами, распределенные транзакции и шаблоны для работы с большими объемами систем. Мы относимся к данным SQL с NoSQL. Мы рассматривали возможности хранения данных, доступные в Azure, которые включают в себя как ориентированный на Майкрософт, так и вариант с открытым кодом. Наконец, мы обсуждали кэширование и Elasticsearch в облачном приложении.

### <a name="references"></a>Ссылки

- [Шаблон разделение команд и запросов (CQRS)](https://docs.microsoft.com/azure/architecture/patterns/cqrs)

- [Event Sourcing pattern](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing) (Шаблон источников событий)

- [Реляционные СУБД и базы данных NoSQL: обзор](https://maxivak.com/rdbms-vs-nosql-databases/)

- [Почему не существует отказоустойчивых секций РСУБД в Теоремае CAP и почему она доступна?](https://stackoverflow.com/questions/36404765/why-isnt-rdbms-partition-tolerant-in-cap-theorem-and-why-is-it-available)

- [Материализованный вид](https://docs.microsoft.com/azure/architecture/patterns/materialized-view)

- [Все, что действительно необходимо знать о базах данных с открытым исходным кодом](https://www.ibm.com/blogs/systems/all-you-really-need-to-know-about-open-source-databases/)

- [Шаблон компенсирующих транзакций](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Шаблон Saga](https://microservices.io/patterns/data/saga.html)

- [Шаблоны Saga | Реализация бизнес-транзакций с помощью микрослужб](https://blog.couchbase.com/saga-pattern-implement-business-transactions-using-microservices-part/)

- [Шаблон компенсирующих транзакций](https://docs.microsoft.com/azure/architecture/patterns/compensating-transaction)

- [Знакомство с 9-шариком: Cosmos DB уровней согласованности](https://blog.jeremylikness.com/blog/2018-03-23_getting-behind-the-9ball-cosmosdb-consistency-levels/)

- [Изучение различных типов баз данных NoSQL, часть II](https://www.3pillarglobal.com/insights/exploring-the-different-types-of-nosql-databases)

- [Для баз данных RDBMS, NoSQL и Невскл. Собеседование с Джон Райан](http://www.odbms.org/blog/2018/03/on-rdbms-nosql-and-newsql-databases-interview-with-john-ryan/)
  
- [Сравнение SQL VS NoSQL и Невскл. полное сравнение](https://www.xenonstack.com/blog/sql-vs-nosql-vs-newsql/)

- [ТИРЕ: четыре свойства баз данных Kubernetes — Native](https://thenewstack.io/dash-four-properties-of-kubernetes-native-databases/)

- [коккроачдб](https://www.cockroachlabs.com/)

- [тидб](https://pingcap.com/en/)

- [югабитедб](https://www.yugabyte.com/)

- [витесс](https://vitess.io/)

- [Elasticsearch: полное руководство](http://shop.oreilly.com/product/0636920028505.do)
  
- [Введение в Apache Lucene](https://www.baeldung.com/lucene)

>[!div class="step-by-step"]
>[Назад](azure-caching.md)
>[Вперед](resiliency.md) <!-- Next Chapter -->
