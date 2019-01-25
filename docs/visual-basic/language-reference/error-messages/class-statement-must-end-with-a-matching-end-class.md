---
title: '&#39;Класс&#39; оператор должен заканчиваться соответствующим &#39;End Class&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 4e80ce58048bfa7f2fecc65e7167479df07bf57c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715092"
---
# <a name="39class39-statement-must-end-with-a-matching-39end-class39"></a>&#39;Класс&#39; оператор должен заканчиваться соответствующим &#39;End Class&#39;
`Class` используется для запуска `Class` block; поэтому он может присутствовать только в начале блока, соответствующий `End Class` инструкции, завершать этот блок. Либо имеется лишний оператор `Class` инструкции, или не заканчивается на `Class` блоке с `End Class`.  
  
 **Идентификатор ошибки:** BC30481  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Найдите и удалите ненужный оператор `Class` .  
  
-   В заключение `Class` блок с соответствующим `End Class`.  
  
## <a name="see-also"></a>См. также
- [Конец \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
