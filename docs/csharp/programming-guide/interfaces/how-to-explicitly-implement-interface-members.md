---
title: Практическое руководство. Руководство по программированию на C#. Явная реализация членов интерфейса
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 5ef8b42fe5ca07548d52b88720ea4845d2408bb1
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69589204"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>Практическое руководство. Руководство по программированию на C#. Явная реализация членов интерфейса
В этом примере объявляются [интерфейс](../../language-reference/keywords/interface.md) `IDimensions` и класс `Box`, который явно реализует члены интерфейса `getLength` и `getWidth`. Доступ к членам осуществляется посредством экземпляра интерфейса `dimensions`.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
  
- Обратите внимание, что следующие строки в методе `Main` закомментированы, поскольку при их компиляции возникнут ошибки. Член интерфейса, реализованный явным образом, недоступен из экземпляра [класса](../../language-reference/keywords/class.md):  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- Также обратите внимание, что следующие строки в методе `Main` успешно выводят на печать размеры поля, поскольку методы вызываются из экземпляра интерфейса:  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Классы и структуры](../classes-and-structs/index.md)
- [Интерфейсы](./index.md)
- [Практическое руководство. Явная реализация элементов двух интерфейсов](./how-to-explicitly-implement-members-of-two-interfaces.md)
