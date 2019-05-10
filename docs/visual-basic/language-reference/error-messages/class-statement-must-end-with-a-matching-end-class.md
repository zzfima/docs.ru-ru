---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 559595e9902ec2f0a19fd6b13e2c89fa1c2b52d7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64602415"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a>Оператор Class должен заканчиваться соответствующим End Class
`Class` используется для запуска `Class` block; поэтому он может присутствовать только в начале блока, соответствующий `End Class` инструкции, завершать этот блок. Либо имеется лишний оператор `Class` инструкции, или не заканчивается на `Class` блоке с `End Class`.  
  
 **Идентификатор ошибки:** BC30481  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Найдите и удалите ненужный оператор `Class` .  
  
- В заключение `Class` блок с соответствующим `End Class`.  
  
## <a name="see-also"></a>См. также

- [Конец \<ключевое слово > инструкции](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
- [Оператор Class](../../../visual-basic/language-reference/statements/class-statement.md)
