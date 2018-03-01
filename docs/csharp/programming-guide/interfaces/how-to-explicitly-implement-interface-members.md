---
title: "Практическое руководство. Явная реализация членов интерфейса (Руководство по программированию на C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e02ae26000057e4e7323a777a6a0e1ca6fd8871b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>Практическое руководство. Явная реализация членов интерфейса (Руководство по программированию на C#)
В этом примере объявляются [интерфейс](../../../csharp/language-reference/keywords/interface.md) `IDimensions` и класс `Box`, который явно реализует члены интерфейса `getLength` и `getWidth`. Доступ к членам осуществляется посредством экземпляра интерфейса `dimensions`.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideInheritance#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_1.cs)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
-   Обратите внимание, что следующие строки в методе `Main` закомментированы, поскольку при их компиляции возникнут ошибки. Член интерфейса, реализованный явным образом, недоступен из экземпляра [класса](../../../csharp/language-reference/keywords/class.md):  
  
     [!code-csharp[csProgGuideInheritance#45](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_2.cs)]  
  
-   Также обратите внимание, что следующие строки в методе `Main` успешно выводят на печать размеры поля, поскольку методы вызываются из экземпляра интерфейса:  
  
     [!code-csharp[csProgGuideInheritance#46](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-explicitly-implement-interface-members_3.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)  
 [Практическое руководство. Явная реализация членов двух интерфейсов](../../../csharp/programming-guide/interfaces/how-to-explicitly-implement-members-of-two-interfaces.md)
