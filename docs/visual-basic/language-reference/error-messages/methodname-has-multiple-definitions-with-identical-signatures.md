---
title: Метод <methodname> несколько раз определен с одинаковыми подписями
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 97113227591c40f302d3d1a08a4248a8199817bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285432"
---
# <a name="methodname-has-multiple-definitions-with-identical-signatures"></a>"\<имя_метода >" имеет несколько определений с одинаковыми сигнатурами
Объект `Function` или `Sub` в объявлении процедуры используются одинаковые процедуры имя и список аргументов, как и в предыдущем объявлении. Одной из возможных причин является попытка перегрузить исходный текст процедуры. Перегруженные процедуры должны иметь разные списки аргументов.  
  
 **Идентификатор ошибки:** BC30269  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените имя процедуры или список аргументов, или удалите повторяющееся объявление.  
  
## <a name="see-also"></a>См. также
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Вопросы, связанные с перегрузкой процедур](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
