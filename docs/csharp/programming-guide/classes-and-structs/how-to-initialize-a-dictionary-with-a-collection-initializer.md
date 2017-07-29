---
title: "Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#)."
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41d6a9934daaa1274901e20de58cfd480c904bfa
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (Руководство по программированию на C#).
Метод <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> принимает два параметра: один для ключа и один для значения. Для инициализации <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add` которой принимает несколько параметров, следует заключить каждый набор параметров в скобки, как показано в приведенном ниже примере.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName`.  
  
 [!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]  
  
 Обратите внимание на две пары фигурных скобок в каждом элементе коллекции. Внутренняя пара фигурных скобок заключает инициализатор объекта `StudentName`, а внешняя пара — инициализатор пары "ключ-значение", которая будет добавлена в коллекцию `students`<xref:System.Collections.Generic.Dictionary`2>. И наконец, весь инициализатор коллекции для словаря заключается в фигурные скобки.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, которое было создано в [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]. По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и содержит ссылку на библиотеку System.Core.dll и директиву using для пространства имен System.Linq. Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.   
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

