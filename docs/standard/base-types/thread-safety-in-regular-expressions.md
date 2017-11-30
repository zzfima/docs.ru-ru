---
title: "Потокобезопасность в регулярных выражениях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4cfa24da8083eac01275ad76f5c2db974b39a25
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="thread-safety-in-regular-expressions"></a>Потокобезопасность в регулярных выражениях
<xref:System.Text.RegularExpressions.Regex> Сам класс является потокобезопасным и неизменяемым (только для чтения). Это означает, что объекты **Regex** могут создаваться в любом потоке и совместно использоваться несколькими потоками. Одни и те же методы могут вызываться из любого потока, никак не изменяя при этом глобальное состояние.  
  
 Однако объекты результатов (**соответствия** и **MatchCollection**) возвращенные **Regex** должны использоваться в одном потоке. Несмотря на то, что по своей логике многие из этих объектов неизменяемы, их реализации способны задерживать вычисление некоторых результатов для повышения эффективности работы, поэтому в итоге вызывающим объектам приходится сериализовывать доступ к ним.  
  
 Если доступ к объектам результатов **Regex** необходимо предоставить нескольким потокам, то эти объекты можно преобразовать в потокобезопасные, вызвав их синхронизированные методы. Все классы регулярных выражений, за исключением перечислителей, являются потокобезопасными или же могут быть преобразованы в потокобезопасные объекты с помощью синхронизированных методов.  
  
 Перечислители являются единственным исключением. Вызовы, обращенные к перечислителям коллекций, в приложениях должны быть сериализованы. Правило заключается в том, что если существует возможность одновременной работы перечислителей из нескольких потоков с одной коллекцией, то их методы необходимо синхронизировать в корневом объекте коллекции, по которой проходит перечислитель.  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)
