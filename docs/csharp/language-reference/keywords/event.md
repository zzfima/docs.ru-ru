---
title: Справочник по C#. event
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
ms.openlocfilehash: a6a62881f7205891bafe039a42da44eb8f8d03c0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422827"
---
# <a name="event-c-reference"></a>event (Справочник по C#)
Ключевое слово `event` используется для объявления события в классе Publisher.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует объявление и вызов события, которое использует <xref:System.EventHandler> как базовый тип делегата. Полный пример кода, демонстрирующий использование универсального типа делегата <xref:System.EventHandler%601>, создание подписки на событие и создание метода обработчика событий, см. в практическом руководстве по [ публикации событий в соответствии с рекомендациями по .NET Framework](../../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).  
  
 [!code-csharp[csrefKeywordsModifiers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#7)]
  
 События представляют собой специальный вид многоадресного делегата, который можно вызвать только из класса или структуры, в которых он объявлен (класс Publisher). Если другие классы или структуры подписываются на событие, их методы обработчиков событий будут вызываться, когда класс Publisher будет вызывать событие. Дополнительные сведения и примеры кода см. в разделах [События](../../programming-guide/events/index.md) и [Делегаты](../../programming-guide/delegates/index.md).  
  
 События могут иметь пометку [public](./public.md), [private](./private.md), [protected](./protected.md), [internal](./internal.md), [protected internal](./protected-internal.md) или [private protected](./private-protected.md). Эти модификаторы доступа определяют, каким образом пользователи класса смогут получать доступ к событию. Дополнительные сведения см. в статье [Модификаторы доступа](../../programming-guide/classes-and-structs/access-modifiers.md).  
  
## <a name="keywords-and-events"></a>Ключевые слова и события  
 Следующие ключевые слова применяются к событиям.  
  
|Ключевое слово|ОПИСАНИЕ|Дополнительные сведения|  
|-------------|-----------------|--------------------------|  
|[static](./static.md)|Делает событие доступным для вызывающих объектов в любое время, даже если экземпляр класса не существует.|[Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[virtual](./virtual.md)|Позволяет производным классам переопределять поведение события с помощью ключевого слова [override](./override.md).|[Наследование](../../programming-guide/classes-and-structs/inheritance.md)|  
|[sealed](./sealed.md)|Указывает, что для производных классов оно больше не является виртуальным.||  
|[abstract](./abstract.md)|Компилятор не будет создавать блоки доступа к событиям `add` и `remove`, и поэтому производные классы должны предоставлять собственную реализацию.||  
  
 Событие может быть объявлено как статическое событие с помощью ключевого слова [static](./static.md). Это делает событие доступным для вызывающих объектов в любое время, даже если экземпляр класса не существует. Дополнительные сведения см. в статье [Статические классы и члены статических классов](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Событие может быть помечено как виртуальное событие с помощью ключевого слова [virtual](./virtual.md). Это позволяет производным классам переопределять поведение события с помощью ключевого слова [override](./override.md). Дополнительные сведения см. в разделе [Наследование](../../programming-guide/classes-and-structs/inheritance.md). Событие, переопределяющее виртуальное событие, также может быть запечатанным ([sealed](./sealed.md)), что указывает, что для производных классов оно больше не является виртуальным. И наконец, можно объявить событие абстрактным ([abstract](./abstract.md)), что означает, что компилятор не будет создавать блоки доступа к событиям `add` и `remove`. Поэтому производные классы должны предоставлять собственную реализацию.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Ключевые слова в C#](./index.md)
- [add](./add.md)
- [remove](./remove.md)
- [Модификаторы](index.md)
- [Практическое руководство. Объединение делегатов (многоадресные делегаты)](../../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
