---
title: Индексаторы (Руководство по программированию в C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5397462994d5e684406c6de65c4f31d9d20eef22
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="indexers-c-programming-guide"></a>Индексаторы (Руководство по программированию в C#)

Индексаторы позволяют индексировать экземпляры класса или структуры точно так же, как и массивы. Индексированное значение можно задавать или получать без явного указания типа или экземпляра элемента. Индексаторы действуют как [свойства](../../../csharp/programming-guide/classes-and-structs/properties.md), за исключением того, что их акцессоры принимают параметры.  
 
 В следующем примере определяется универсальный класс с простыми акцессорами [get](../../../csharp/language-reference/keywords/get.md) и [set](../../../csharp/language-reference/keywords/set.md) для назначения и получения значений. Класс `Program` создает экземпляр этого класса для хранения строк.  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  Дополнительные примеры см. в разделе [Связанные разделы](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).  
  
## <a name="expression-body-definitions"></a>Определения текста выражений  
 
Довольно часто акцессор get или set индексатора состоит из одной инструкции, которая просто возвращает или задает значение. Члены, воплощающие выражение, предоставляют упрощенный синтаксис для поддержки такого варианта использования. Начиная с версии C# 6, доступные только для чтения индексаторы можно реализовать в виде члена, воплощающего выражение, как показано в следующем примере.

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

Обратите внимание, что `=>` представляет тело выражения, а ключевое слово `get` не используется. 

Начиная с версии C# 7.0, методы доступа get и set можно реализовывать в виде членов с телом в виде выражения. В этом случае необходимо указывать оба ключевых слова (`get` и `set`). Пример:

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a>Общие сведения об индексаторах  
  
-   Индексаторы позволяют индексировать объекты так же, как и массивы.  
  
-   Метод доступа `get` возвращает значение. Метод доступа `set` назначает значение.  
  
-   Ключевое слово [this](../../../csharp/language-reference/keywords/this.md) используется для определения индексаторов.  
  
-   Ключевое слово [value`set` используется для определения значения, присваиваемого индексатором ](../../../csharp/language-reference/keywords/value.md).  
  
-   Индексаторы не нужно индексировать по целому значению; пользователь может определить конкретный механизм поиска на свое усмотрение.  
  
-   Индексаторы могут быть перегружены.  
  
-   Индексаторы могут иметь более одного формального параметра, например при доступе к двумерному массиву.  
  
##  <a name="BKMK_RelatedSections"></a> Связанные разделы  
  
-   [Использование индексаторов](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [Индексаторы в интерфейсах](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [Сравнение свойств и индексаторов](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [Ограничение доступности методов доступа](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md)
