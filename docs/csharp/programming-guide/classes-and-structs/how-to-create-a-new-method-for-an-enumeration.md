---
title: Практическое руководство. Руководство по программированию на C#. Создание метода для перечисления
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 99a2005e1a64fa214776145a903341fb162f0633
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597041"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>Практическое руководство. Руководство по программированию на C#. Создание метода для перечисления
Методы расширения позволяют добавить функциональные возможности, характерные для определенного типа перечисления.  
  
## <a name="example"></a>Пример  
 В следующем примере перечисление `Grades` содержит возможные буквенные оценки, которые учащийся может получить в классе. Метод расширения с именем `Passing` добавляется в тип `Grades`, чтобы каждый экземпляр этого типа "знал", проходной это балл или нет.  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 Обратите внимание на то, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, а возвращаемое значение метода расширения отражает текущее значение этой переменной. Это показывает, что в фоновом режиме методы расширения вызываются непосредственно для статического класса, в котором они определены.  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Методы расширения](./extension-methods.md)
