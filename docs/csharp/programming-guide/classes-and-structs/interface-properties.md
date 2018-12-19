---
title: Руководство по программированию на C#. Свойства интерфейса
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: c51064f9bb5e834648e0086fd8d28f9c0bd84b61
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241591"
---
# <a name="interface-properties-c-programming-guide"></a>Свойства интерфейса (Руководство по программированию на C#)
Свойства можно объявлять для [интерфейса](../../../csharp/language-reference/keywords/interface.md). Ниже показан пример метода доступа к свойству интерфейса:  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 Метод доступа свойства интерфейса не имеет тела. Таким образом, методы доступа нужны, чтобы указать, доступно ли свойство для чтения и записи, только для чтения или только для записи.  
  
## <a name="example"></a>Пример  
 В этом примере интерфейс `IEmployee` содержит доступное для чтения и записи свойство `Name`, а также свойство `Counter`, предназначенное только для чтения. Класс `Employee` реализует интерфейс `IEmployee` и использует эти два свойства. Программа считывает имя нового сотрудника и текущее число сотрудников, после чего отображает имя сотрудника и его рассчитанный номер.  
  
 Вы можете использовать полное имя свойства, которое ссылается на интерфейс, где был объявлен член. Пример:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 Это называется [явной реализацией интерфейса](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md). Например, если класс `Employee` реализует два интерфейса (`ICitizen` и `IEmployee`), оба из которых содержат свойство `Name`, потребуется явная реализация члена интерфейса. Это значит, что потребуется следующее объявление свойства:  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 реализует свойство `Name` в интерфейсе `IEmployee`, тогда как следующее объявление:  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 реализует свойство `Name` в интерфейсе `ICitizen`.  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a>Пример результатов выполнения  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [Использование свойств](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
- [Сравнение свойств и индексаторов](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
- [Индексаторы](../../../csharp/programming-guide/indexers/index.md)  
- [Интерфейсы](../../../csharp/programming-guide/interfaces/index.md)
