---
title: Как выполнить Руководство по программированию на C#. Инициализация объектов с помощью инициализатора объектов.
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 29987b9ba1f1f18f4e768766bd2391ebb5862f97
ms.sourcegitcommit: d09c77414e9e4fc72c79b04deee7a756a120674e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2019
ms.locfileid: "54084879"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Инициализация объектов с помощью инициализатора объектов.

Инициализаторы объектов можно использовать для декларативной инициализации объектов типов без явного вызова конструктора для типа.  
  
Следующие примеры демонстрируют использование инициализаторов объектов с именованными объектами. Компилятор выполняет обработку инициализаторов объектов, сначала получая доступ к конструктору экземпляра по умолчанию, а затем обрабатывая инициализации членов. Таким образом, если конструктор по умолчанию объявляется как `private` в классе, произойдет сбой инициализаторов объектов, требующих открытого доступа.
  
При определении анонимного типа использовать инициализатор объекта обязательно. Дополнительные сведения см. в разделе [Как Возвращение подмножества свойств элементов в запросе](how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Пример  

В следующем примере показана инициализация нового типа `StudentName` с помощью инициализаторов объектов. В этом примере задаются свойства в типе `StudentName`:
  
[!code-csharp-interactive[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

Инициализаторы объектов можно использовать для задания индексаторов в объекте. В следующем примере определяется класс `BaseballTeam`, который использует индексатор для получения и задания игроков в различных положениях. Инициализатор может назначать игроков в зависимости от сокращенного обозначения положения или номера, используемого для каждой позиции в бейсбольных карточках.

[!code-csharp-interactive[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a>См. также раздел

- [Руководство по программированию на C#](../index.md)  
- [Инициализаторы объектов и коллекций](object-and-collection-initializers.md)
