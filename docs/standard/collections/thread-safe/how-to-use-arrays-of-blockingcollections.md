---
title: Практическое руководство. Использование массивов для блокировки коллекций в конвейере
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9313f1064534702fdc2d239eb7f0f69a470329e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a>Практическое руководство. Использование массивов для блокировки коллекций в конвейере
В приведенном ниже примере показано, как использовать массивы объектов <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> со статическими методами, например методами <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, для реализации быстрой и гибкой передачи данных между компонентами.  
  
## <a name="example"></a>Пример  
 В следующем примере показана основная реализация конвейера, в котором каждый объект выполняет параллельную операцию получения данных из входной коллекции, выполняет их преобразование и передает их в выходную коллекцию.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)
