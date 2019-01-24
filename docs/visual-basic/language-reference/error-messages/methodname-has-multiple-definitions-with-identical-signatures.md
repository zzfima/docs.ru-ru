---
title: '&#39;&lt;имя_метода&gt; &#39; имеет несколько определений с одинаковыми сигнатурами'
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: daa1bc4fcc3ee0fe0279a029f9aac03d4555d582
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536949"
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a>&#39;&lt;имя_метода&gt; &#39; имеет несколько определений с одинаковыми сигнатурами
Объект `Function` или `Sub` в объявлении процедуры используются одинаковые процедуры имя и список аргументов, как и в предыдущем объявлении. Одной из возможных причин является попытка перегрузить исходный текст процедуры. Перегруженные процедуры должны иметь разные списки аргументов.  
  
 **Идентификатор ошибки:** BC30269  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените имя процедуры или список аргументов, или удалите повторяющееся объявление.  
  
## <a name="see-also"></a>См. также
- [Ссылки на объявленные элементы](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Вопросы, связанные с перегрузкой процедур](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
