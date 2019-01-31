---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 572e1d74810aad6d24e6eefc8d37729f5dc950c9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286953"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>Оператор Class должен заканчиваться соответствующим End Class
`Class` используется для запуска `Class` block; поэтому он может присутствовать только в начале блока, соответствующий `End Class` инструкции, завершать этот блок. Либо имеется лишний оператор `Class` инструкции, или не заканчивается на `Class` блоке с `End Class`.  
  
 **Идентификатор ошибки:** BC30481  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Найдите и удалите ненужный оператор `Class` .  
  
-   В заключение `Class` блок с соответствующим `End Class`.  
  
## <a name="see-also"></a>См. также
- [Конец \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
