---
title: Как выполнить Руководство по программированию на C#. Инициализация объектов с помощью инициализатора объектов.
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 82efa751ad70fd2741ec2e306f56f2be06abad11
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245002"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Инициализация объектов с помощью инициализатора объектов.
Инициализаторы объектов можно использовать для декларативной инициализации объектов типов без явного вызова конструктора для типа.  
  
 Следующие примеры демонстрируют использование инициализаторов объектов с именованными объектами. Компилятор выполняет обработку инициализаторов объектов, сначала получая доступ к конструктору экземпляра по умолчанию, а затем обрабатывая инициализации членов. Таким образом, если конструктор по умолчанию объявляется как `private` в классе, произойдет сбой инициализаторов объектов, требующих открытого доступа.  
  
 При определении анонимного типа использовать инициализатор объекта обязательно. Дополнительные сведения см. в статье [Практическое руководство. Возвращение подмножества свойств элементов в запросе](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показана инициализация нового типа `StudentName` с помощью инициализаторов объектов.  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере показана инициализация коллекции типов `StudentName` с помощью инициализатора коллекции. Обратите внимание, что инициализатор коллекции представляет собой ряд инициализаторов объектов с разделителями-запятыми.  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот код, скопируйте и вставьте класс в проект консольного приложения Visual C#, созданный в Visual Studio.  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Инициализаторы объектов и коллекций](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
