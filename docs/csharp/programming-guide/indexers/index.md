---
title: Руководство по программированию на C#. Индексаторы
ms.date: 03/10/2017
f1_keywords:
- cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
ms.openlocfilehash: c00f506a682ec5d9805537b80159fd41d2174b67
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75702952"
---
# <a name="indexers-c-programming-guide"></a>Индексаторы (Руководство по программированию в C#)

Индексаторы позволяют индексировать экземпляры класса или структуры точно так же, как и массивы. Индексированное значение можно задавать или получать без явного указания типа или экземпляра элемента. Индексаторы действуют как [свойства](../classes-and-structs/properties.md), за исключением того, что их акцессоры принимают параметры.  

 В следующем примере определяется универсальный класс с простыми акцессорами [get](../../language-reference/keywords/get.md) и [set](../../language-reference/keywords/set.md) для назначения и получения значений. Класс `Program` создает экземпляр этого класса для хранения строк.  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
> Дополнительные примеры см. в разделе [Связанные разделы](./index.md#BKMK_RelatedSections).  
  
## <a name="expression-body-definitions"></a>Определения текста выражений  
 
Довольно часто акцессор get или set индексатора состоит из одной инструкции, которая просто возвращает или задает значение. Члены, воплощающие выражение, предоставляют упрощенный синтаксис для поддержки такого варианта использования. Начиная с версии C# 6, доступные только для чтения индексаторы можно реализовать в виде члена, воплощающего выражение, как показано в следующем примере.

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

Обратите внимание, что `=>` представляет тело выражения, а ключевое слово `get` не используется. 

Начиная с версии C# 7.0, методы доступа get и set можно реализовывать в виде членов с телом в виде выражения. В этом случае необходимо указывать оба ключевых слова (`get` и `set`). Пример:

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a>Общие сведения об индексаторах  
  
- Индексаторы позволяют индексировать объекты так же, как и массивы.  
  
- Метод доступа `get` возвращает значение. Метод доступа `set` назначает значение.  
  
- Ключевое слово [this](../../language-reference/keywords/this.md) используется для определения индексаторов.  
  
- Ключевое слово [value`set` используется для определения значения, присваиваемого индексатором ](../../language-reference/keywords/value.md).  
  
- Индексаторы не нужно индексировать по целому значению; пользователь может определить конкретный механизм поиска на свое усмотрение.  
  
- Индексаторы могут быть перегружены.  
  
- Индексаторы могут иметь более одного формального параметра, например при доступе к двумерному массиву.  
  
## <a name="BKMK_RelatedSections"></a> Связанные разделы  
  
- [Использование индексаторов](./using-indexers.md)  
  
- [Индексаторы в интерфейсах](./indexers-in-interfaces.md)  
  
- [Сравнение свойств и индексаторов](./comparison-between-properties-and-indexers.md)  
  
- [Ограничение доступности методов доступа](../classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  

Дополнительные сведения см. в разделе [Индексаторы](~/_csharplang/spec/classes.md#indexers) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction). Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Свойства](../classes-and-structs/properties.md)
