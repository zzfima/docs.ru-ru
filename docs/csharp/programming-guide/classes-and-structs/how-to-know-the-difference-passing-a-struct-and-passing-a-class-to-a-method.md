---
title: Как выполнить Руководство по программированию на C#. Определение различия между передачей структуры и ссылки класса в метод
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- structs [C#], passing as method parameter
- passing parameters [C#], structs vs. classes
- methods [C#], passing classes vs. structs
ms.assetid: 9c1313a6-32a8-4ea7-a59f-450f66af628b
ms.openlocfilehash: c5963f45ee233f4413c4281a063c9c3d2a4c2a93
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245458"
---
# <a name="how-to-know-the-difference-between-passing-a-struct-and-passing-a-class-reference-to-a-method-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Определение различия между передачей структуры и ссылки класса в метод
В следующем примере демонстрируется, чем передача [структуры](../../../csharp/language-reference/keywords/struct.md) в метод отличается от передачи экземпляра [класса](../../../csharp/language-reference/keywords/class.md) в метод. В этом примере оба аргумента (структура и экземпляр класса) передаются по значению, и оба метода изменяют значение одного поля аргумента. Тем не менее результаты этих двух методов будут отличаться, поскольку в случае со структурой передаваемое содержимое отличается от передачи экземпляра класса.  
  
 Поскольку структура является [типом значения](../../../csharp/language-reference/keywords/value-types.md), при [передаче структуры по значению](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md) в метод этот метод получает и обрабатывает копию аргумента структуры. При этом метод не имеет доступа к исходной структуре в вызывающем методе и, соответственно, никак не может изменить ее. В этом случае метод может изменять только копию.  
  
 Экземпляр класса является [ссылочным типом](../../../csharp/language-reference/keywords/reference-types.md), а не типом значения. При [передаче ссылочного типа по значению](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md) в метод этот метод получает копию ссылки на экземпляр класса. Таким образом, метод получает копию адреса экземпляра, а не копию самого экземпляра. Экземпляр класса в вызывающем методе содержит адрес, а параметр в вызываемом методе — копию этого адреса, которая ссылается на тот же объект. Поскольку параметр содержит только копию адреса, вызываемый метод не может изменить адрес экземпляра класса в вызывающем методе. Тем не менее вызываемый метод может обращаться по исходному адресу и его копии к членам класса. Если вызываемый метод изменяет член класса, также изменится исходный экземпляр класса в вызывающем методе.  
  
 Различия демонстрируются в выходных данных следующего примера. Значение поля `willIChange` экземпляра класса изменяется в результате вызова метода `ClassTaker`, поскольку этот метод находит указанное поле экземпляра класса по адресу, содержащемуся в параметре. Поле `willIChange` структуры в вызывающем методе не изменяется в результате вызова метода `StructTaker`, поскольку значением аргумента является копия самой структуры, а не ее адреса. `StructTaker` изменяет саму копию, которая будет утрачена после завершения вызова `StructTaker`.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideObjects#32](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Классы](../../../csharp/programming-guide/classes-and-structs/classes.md)  
- [Структуры](../../../csharp/programming-guide/classes-and-structs/structs.md)  
- [Передача параметров](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)
