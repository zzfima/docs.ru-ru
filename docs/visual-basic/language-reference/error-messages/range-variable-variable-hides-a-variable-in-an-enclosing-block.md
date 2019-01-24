---
title: Переменная диапазона &lt;переменной&gt; скрывает переменную во внешнем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса
ms.date: 07/20/2015
f1_keywords:
- bc36633
- vbc36633
helpviewer_keywords:
- BC36633
ms.assetid: 5d5470e4-3de5-49c2-8831-1087625f4a77
ms.openlocfilehash: aef52ea912a4180a6505949c8077296628592c72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54748120"
---
# <a name="range-variable-ltvariablegt-hides-a-variable-in-an-enclosing-block-a-previously-defined-range-variable-or-an-implicitly-declared-variable-in-a-query-expression"></a>Переменная диапазона &lt;переменной&gt; скрывает переменную во внешнем блоке, ранее определенную переменную диапазона или неявно объявленную переменную в выражении запроса
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
