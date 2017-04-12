---
title: "Место (Visual Basic) в стеке | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6343767da28ea4e02f9443006b222640755f7882
ms.lasthandoff: 03/13/2017

---
# <a name="out-of-stack-space-visual-basic"></a>Отсутствует место в стеке (Visual Basic)
Стек — это рабочая область памяти, увеличивается и уменьшается динамически с требованиями выполняемой программы. Предел был превышен.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте, что процедуры не вложены слишком глубоко.  
  
2.  Убедитесь, что рекурсивные процедуры завершаются должным образом.  
  
3.  Если для локальных переменных недостаточно места, чем доступно, объявите некоторые переменные на уровне модуля. Можно также объявить все переменные в процедуре статических перед `Property`, `Sub`, или `Function` ключевого слова with `Static`. Или можно использовать `Static` инструкции для объявления в процедурах отдельных статических переменных.  
  
4.  Переопределите некоторые строки фиксированной длины как строки переменной длины, как строки фиксированной длины используют большее пространство стека, чем строки с переменной длиной. Можно также определить строку на уровне модуля, где требуется пространство стека.  
  
5.  Проверьте число вложенных `DoEvents` вызовы функций, с помощью `Calls` диалоговое окно просмотра процедур, действующих в стеке.  
  
6.  Убедитесь, что не был запущен «Каскад событий» путем активации события, вызывающего процедуру события уже в стеке. Каскад событий похож на вызов незаконченной рекурсивной процедуры, но это заметен, поскольку вызов выполняется системой [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вместо явного вызова в коде. Используйте `Calls`диалоговое окно просмотра процедур, действующих в стеке.  
  
## <a name="see-also"></a>См. также  
 [Окно памяти](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
