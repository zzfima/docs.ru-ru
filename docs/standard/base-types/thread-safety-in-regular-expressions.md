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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 804f83d85206b5f49a0bea290f281b36e18bb847
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="thread-safety-in-regular-expressions"></a>Потокобезопасность в регулярных выражениях
Сам по себе класс <xref:System.Text.RegularExpressions.Regex> является потокобезопасным и неизменяемым (предназначенным только для чтения). Это означает, что объекты **Regex** могут создаваться в любом потоке и совместно использоваться несколькими потоками. Одни и те же методы могут вызываться из любого потока, никак не изменяя при этом глобальное состояние.  
  
 Тем не менее, объекты результатов (**Match** и **MatchCollection)**, возвращаемые **Regex**, следует использовать только в одном потоке. Несмотря на то, что по своей логике многие из этих объектов неизменяемы, их реализации способны задерживать вычисление некоторых результатов для повышения эффективности работы, поэтому в итоге вызывающим объектам приходится сериализовывать доступ к ним.  
  
 Если доступ к объектам результатов **Regex** необходимо предоставить нескольким потокам, то эти объекты можно преобразовать в потокобезопасные, вызвав их синхронизированные методы. Все классы регулярных выражений, за исключением перечислителей, являются потокобезопасными или же могут быть преобразованы в потокобезопасные объекты с помощью синхронизированных методов.  
  
 Перечислители являются единственным исключением. Вызовы, обращенные к перечислителям коллекций, в приложениях должны быть сериализованы. Правило заключается в том, что если существует возможность одновременной работы перечислителей из нескольких потоков с одной коллекцией, то их методы необходимо синхронизировать в корневом объекте коллекции, по которой проходит перечислитель.  
  
## <a name="see-also"></a>См. также  
 [Регулярные выражения .NET](../../../docs/standard/base-types/regular-expressions.md)
