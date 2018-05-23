---
title: Потокобезопасность в регулярных выражениях
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET Framework regular expressions, threads
- regular expressions, threads
- searching with regular expressions, threads
- parsing text with regular expressions, threads
- pattern-matching with regular expressions, threads
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79ca0b92cf79ca9be023925f064c1c7c16b3c9ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="thread-safety-in-regular-expressions"></a><span data-ttu-id="1cdc1-102">Потокобезопасность в регулярных выражениях</span><span class="sxs-lookup"><span data-stu-id="1cdc1-102">Thread Safety in Regular Expressions</span></span>
<span data-ttu-id="1cdc1-103">Сам по себе класс <xref:System.Text.RegularExpressions.Regex> является потокобезопасным и неизменяемым (предназначенным только для чтения).</span><span class="sxs-lookup"><span data-stu-id="1cdc1-103">The <xref:System.Text.RegularExpressions.Regex> class itself is thread safe and immutable (read-only).</span></span> <span data-ttu-id="1cdc1-104">Это означает, что объекты **Regex** могут создаваться в любом потоке и совместно использоваться несколькими потоками. Одни и те же методы могут вызываться из любого потока, никак не изменяя при этом глобальное состояние.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-104">That is, **Regex** objects can be created on any thread and shared between threads; matching methods can be called from any thread and never alter any global state.</span></span>  
  
 <span data-ttu-id="1cdc1-105">Тем не менее, объекты результатов (**Match** и **MatchCollection)**, возвращаемые **Regex**, следует использовать только в одном потоке.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-105">However, result objects (**Match** and **MatchCollection**) returned by **Regex** should be used on a single thread.</span></span> <span data-ttu-id="1cdc1-106">Несмотря на то, что по своей логике многие из этих объектов неизменяемы, их реализации способны задерживать вычисление некоторых результатов для повышения эффективности работы, поэтому в итоге вызывающим объектам приходится сериализовывать доступ к ним.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-106">Although many of these objects are logically immutable, their implementations could delay computation of some results to improve performance, and as a result, callers must serialize access to them.</span></span>  
  
 <span data-ttu-id="1cdc1-107">Если доступ к объектам результатов **Regex** необходимо предоставить нескольким потокам, то эти объекты можно преобразовать в потокобезопасные, вызвав их синхронизированные методы.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-107">If there is a need to share **Regex** result objects on multiple threads, these objects can be converted to thread-safe instances by calling their synchronized methods.</span></span> <span data-ttu-id="1cdc1-108">Все классы регулярных выражений, за исключением перечислителей, являются потокобезопасными или же могут быть преобразованы в потокобезопасные объекты с помощью синхронизированных методов.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-108">With the exception of enumerators, all regular expression classes are thread safe or can be converted into thread-safe objects by a synchronized method.</span></span>  
  
 <span data-ttu-id="1cdc1-109">Перечислители являются единственным исключением.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-109">Enumerators are the only exception.</span></span> <span data-ttu-id="1cdc1-110">Вызовы, обращенные к перечислителям коллекций, в приложениях должны быть сериализованы.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-110">An application must serialize calls to collection enumerators.</span></span> <span data-ttu-id="1cdc1-111">Правило заключается в том, что если существует возможность одновременной работы перечислителей из нескольких потоков с одной коллекцией, то их методы необходимо синхронизировать в корневом объекте коллекции, по которой проходит перечислитель.</span><span class="sxs-lookup"><span data-stu-id="1cdc1-111">The rule is that if a collection can be enumerated on more than one thread simultaneously, you should synchronize enumerator methods on the root object of the collection traversed by the enumerator.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cdc1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="1cdc1-112">See Also</span></span>  
 [<span data-ttu-id="1cdc1-113">Регулярные выражения .NET</span><span class="sxs-lookup"><span data-stu-id="1cdc1-113">.NET Regular Expressions</span></span>](../../../docs/standard/base-types/regular-expressions.md)
