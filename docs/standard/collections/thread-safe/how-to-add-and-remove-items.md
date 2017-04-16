---
title: "Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из этой коллекции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "потокобезопасные коллекции, параллельный словарь"
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Добавление элементов в коллекцию ConcurrentDictionary и их удаление из этой коллекции
В этом примере показано, как выполняется добавление, получение, обновление и удаление элементов из класса <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>.  Этот класс коллекций является потокобезопасной реализацией.  Рекомендуется его использование каждый раз, когда множество потоков одновременно могут попытаться получить доступ к элементам.  
  
 Класс <xref:System.Collections.Concurrent.ConcurrentDictionary%602> предоставляет несколько удобных методов, которые устраняют необходимость создания кода для первоначальной проверки существования ключа перед попыткой добавления или удаления данных.  В таблице ниже перечислены эти удобные методы и приводится описание их использования.  
  
|Метод|Следует использовать в следующих случаях...|  
|-----------|-------------------------------------------------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|Необходимо добавить новое значение для заданного ключа, а также в том случае если ключ уже существует и необходимо заменить его значение.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|Необходимо получить существующее значение для заданного ключа, а также в том случае если ключ не существует и задать значение паре "ключ\-значение".|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A>|Необходимо добавить, получить, обновить или удалить пару "ключ\-значение", а также в том случае, если ключ уже существует или попытка завершилась по какой\-либо причине ошибкой и необходимо выполнить альтернативные действия.|  
  
## Пример  
 В следующем примере два экземпляра класса <xref:System.Threading.Tasks.Task> используются для одновременного добавления некоторых элементов в класс <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, затем выполняется вывод всего содержимого, для того, чтобы показать, что добавление элементов выполнено успешно.  В примере также показано, как использовать методы <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> для добавления, обновления и извлечения элементов из коллекции.  
  
 [!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
 [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]  
  
 Класс <xref:System.Collections.Concurrent.ConcurrentDictionary%602> разработан для многопотоковых сценариев.  Необязательно использовать блокировки в коде для добавления или удаления элементов из коллекции.  Однако всегда есть возможность для одного потока получить значение, а для другого потока немедленно обновить коллекцию, передавая тому же ключу новое значение.  
  
 Кроме того, несмотря на то что все методы <xref:System.Collections.Concurrent.ConcurrentDictionary%602> потокобезопасны, не все методы атомарны, например <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> и <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.  Пользовательский делегат, передаваемый этим методам, вызывается вне внутренней блокировки словаря. \(Это позволяет предотвратить блокировку всех потоков неизвестным кодом.\) Поэтому может произойти следующая последовательность событий.  
  
 1\) Поток A вызывает <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, не находит элемента и создает новый элемент для добавления, вызывая делегат valueFactory.  
  
 2\) Поток B одновременно вызывает <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, делегат valueFactory вызван, этот поток оказывается во внутренней блокировке раньше потока A, его новая пара ключ\-значение добавляется в словарь.  
  
 3\) Пользовательский делегат потока A завершает работу, поток достигает блокировки, но видит, что теперь элемент уже существует.  
  
 4\) Поток A выполняет действие "Get" и возвращает данные, добавленные ранее потоком B.  
  
 Поэтому нет гарантии, что данные, возвращаемые методом <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, будут данными, созданными делегатом valueFactory потока.  Аналогичная последовательность событий может иметь место при вызове метода <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.  
  
## См. также  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)