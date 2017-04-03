---
title: "Практическое руководство. Создание нового метода для перечисления (руководство по программированию в C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
caps.latest.revision: 7
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3d15cbcdd81584ea5c6ab40d231183f883a7a805
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a>Практическое руководство. Создание нового метода для перечисления (Руководство по программированию в C#)
Методы расширения позволяют добавить функциональные возможности, характерные для определенного типа перечисления.  
  
## <a name="example"></a>Пример  
 В следующем примере перечисление `Grades` содержит возможные буквенные оценки, которые учащийся может получить в классе. Метод расширения с именем `Passing` добавляется в тип `Grades`, чтобы каждый экземпляр этого типа "знал", проходной это балл или нет.  
  
 [!code-cs[csProgGuideExtensionMethods#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-create-a-new-method-for-an-enumeration_1.cs)]  
  
 Обратите внимание на то, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, а возвращаемое значение метода расширения отражает текущее значение этой переменной. Это показывает, что в фоновом режиме методы расширения вызываются непосредственно для статического класса, в котором они определены.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот код, скопируйте и вставьте его в проект консольного приложения Visual C#, созданный в [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)]. По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и содержит ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq. Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.   
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
