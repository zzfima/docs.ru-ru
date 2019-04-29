---
title: Оператор Class должен заканчиваться соответствующим End Class
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: 0619db618abd562bda86836bdd41bbcd6caee0f9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61649898"
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
