---
title: "Практическое руководство. Использование массивов для блокировки коллекций в конвейере"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, blocking collections in pipeline
ms.assetid: a39c7ec3-3ad7-4f4d-8fe4-b3e9dbabe2ed
caps.latest.revision: 8
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8dda929df8e3de907c228bbef85749cba5cabc25
ms.contentlocale: ru-ru
ms.lasthandoff: 09/19/2017

---
# <a name="how-to-use-arrays-of-blocking-collections-in-a-pipeline"></a>Практическое руководство. Использование массивов для блокировки коллекций в конвейере
В приведенном ниже примере показано, как использовать массивы объектов <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> со статическими методами, например методами <xref:System.Collections.Concurrent.BlockingCollection%601.TryAddToAny%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny%2A>, для реализации быстрой и гибкой передачи данных между компонентами.  
  
## <a name="example"></a>Пример  
 В следующем примере показана основная реализация конвейера, в котором каждый объект выполняет параллельную операцию получения данных из входной коллекции, выполняет их преобразование и передает их в выходную коллекцию.  
  
 [!code-csharp[CDS_BlockingCollection#07](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example07.cs#07)]
 [!code-vb[CDS_BlockingCollection#07](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/bcpipeline.vb#07)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Потокобезопасные коллекции](../../../../docs/standard/collections/thread-safe/index.md)

