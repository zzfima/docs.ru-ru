---
title: "Практическое руководство. Синхронизация параллельных операций с барьером"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>Практическое руководство. Синхронизация параллельных операций с барьером
В следующем примере показано, как синхронизация параллельных задач с <xref:System.Threading.Barrier>.  
  
## <a name="example"></a>Пример  
 Следующая программа предназначена для подсчета количества итераций (или этапы), необходимые для двух потоков, чтобы каждый нашел свою половину решения одной фазе, используя алгоритм перемешивания слов. После каждого перемешает свои слова, операция следующего этапа барьера сравнивает два результата, чтобы увидеть, если отображается полное предложение в правильном порядке слова.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 Объект <xref:System.Threading.Barrier> — это объект, который предотвращает индивидуальные задачи в параллельном режиме продолжение, пока все задачи не достигнут барьера. Это полезно при параллельной операции поэтапно и каждый этап требуется синхронизация между задачами. В этом примере осуществляется в два этапа для операции. На первом этапе каждая задача заполняет его часть буфера с данными. После завершения каждой задачи, заполняя его разделе, задача сообщает барьера, можно продолжить и ожиданий. Если все задачи отправили сигналы барьера, будут разблокированы и запускает на втором этапе. Барьер необходим, так как на втором этапе требует, чтобы каждая задача доступ ко всем данным, созданным в этой точке. Без барьера первого выполнения задач может попытаться выполнить чтение из буферов, которое не было заполнено еще другими задачами. Вы можете синхронизировать любое количество этапов таким образом.  
  
## <a name="see-also"></a>См. также  
 [Структуры данных для параллельного программирования](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
