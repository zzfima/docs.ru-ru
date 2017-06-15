---
title: "Практическое руководство. Инициализация словаря с помощью инициализатора коллекции (руководство по программированию на C#) | Документы Майкрософт"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 6c6f15772f098618d63a48ada122b1e98ef5e62d
ms.contentlocale: ru-ru
ms.lasthandoff: 06/15/2017

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
