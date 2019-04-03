---
title: Переменная диапазона <variable> скрывает переменную во включающем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: e31f728de228bea743f6c7b5cbfef3cd73367262
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822717"
---
# <a name="range-variable-variable-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>Переменная диапазона \<переменная > скрывает переменную во внешнем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса
Имя переменной диапазона, указанного в `Select`, `From`, `Aggregate`, или `Let` дублирует имя переменной диапазона, уже указанное ранее в запросе, или имя переменной, неявно объявленный для запроса Например, имя поля или имя агрегатной функции.  
  
 **Идентификатор ошибки:** BC36633  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Убедитесь, что все переменные диапазона в области действия определенного запроса имеют уникальные имена. Запрос можно заключить в круглые скобки, чтобы обеспечить уникальную область для вложенных запросов.  
  
## <a name="see-also"></a>См. также

- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Предложение From](../../../visual-basic/language-reference/queries/from-clause.md)
- [Предложение Let](../../../visual-basic/language-reference/queries/let-clause.md)
- [Предложение Aggregate](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
