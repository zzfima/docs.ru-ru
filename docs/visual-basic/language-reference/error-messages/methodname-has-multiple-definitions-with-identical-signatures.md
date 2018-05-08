---
title: '&#39;&lt;имя_метода&gt; &#39; имеет несколько определений с одинаковыми сигнатурами'
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 059d152cf9c3fae77ab53a4a9248b36d99614c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a>&#39;&lt;имя_метода&gt; &#39; имеет несколько определений с одинаковыми сигнатурами
Объект `Function` или `Sub` в объявлении процедуры используются процедуры одинаковые имя и список аргументов, как и в предыдущем объявлении. Возможной причиной этого может быть попытка перегрузки исходной процедуры. Перегруженные процедуры должны иметь разные списки аргументов.  
  
 **Идентификатор ошибки:** BC30269  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените имя процедуры или список аргументов или удалите повторяющееся объявление.  
  
## <a name="see-also"></a>См. также  
 [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Вопросы, связанные с перегрузкой процедур](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
