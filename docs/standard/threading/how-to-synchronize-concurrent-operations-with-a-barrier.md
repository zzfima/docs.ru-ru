---
title: "How to: Synchronize Concurrent Operations with a Barrier | Microsoft Docs"
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
  - "Barrier, how to use"
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Synchronize Concurrent Operations with a Barrier
В примере ниже продемонстрирована синхронизация параллельных задач с <xref:System.Threading.Barrier>.  
  
## Пример  
 Цель следующей программы в подсчете количества итераций \(или этапов\), необходимых для двух потоков, чтобы каждый нашел свою половину решения на одном и том же этапе, используя алгоритм перемешивания слов случайным образом.  После того как каждый потом перемешает свои слова, операция следующего этапа барьера сравнивает два результата для проверки, стоят ли в правильном порядке слова в полученном предложении.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 <xref:System.Threading.Barrier> представляет собой объект, предотвращающий продолжение выполнения отдельных задач в параллельном режиме, пока все задачи не достигнут барьера.  Такая функция полезна при возникновении параллельного выполнения на этапах и необходимости синхронизации каждого этапа между задачами.  В этом примере на операцию отводится два этапа.  На первом этапе каждая задача заполняет данными свою часть буфера.  По окончании заполнения своей части задача сигнализирует барьеру, что готова к продолжению работы, и переходит в режим ожидания.  После того как все задачи отправили сигналы барьеру, они разблокируются, и начинается второй этап.  Барьер необходим, поскольку для второго этапа требуется, чтобы каждая задача имела доступ ко всем данным, созданным к этому моменту.  Без барьера первые выполняемые задачи могут попытаться выполнить чтение из буферов, которые еще не заполнены другими задачами.  Таким образом можно синхронизировать любое количество этапов.  
  
## См. также  
 [Data Structures for Parallel Programming](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)