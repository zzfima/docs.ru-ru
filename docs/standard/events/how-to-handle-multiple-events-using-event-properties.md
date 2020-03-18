---
title: Практическое руководство. Обработка нескольких событий с помощью их свойств
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: f74d75a09da350b34dfb067c3d0db8fc669116ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124767"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a>Практическое руководство. Обработка нескольких событий с помощью их свойств
Чтобы использовать свойства событий, следует определить свойства событий в классе, который вызывает события, а затем задать делегаты для свойств событий в классах, обрабатывающих события. Для реализации нескольких свойств событий в классе класс должен хранить и обслуживать внутри себя делегата, определенного для каждого события. Типичная стратегия заключается в реализации коллекции делегатов, которая индексируется по ключу события.  
  
 Для сохранения делегатов для каждого события можно воспользоваться классом <xref:System.ComponentModel.EventHandlerList> или реализовать собственную коллекцию. Класс коллекции должен предоставить методы для установки, извлечения делегата обработчика событий и доступа к нему по ключу события. Например, можно использовать класс <xref:System.Collections.Hashtable> или извлечь пользовательский класс от класса <xref:System.Collections.DictionaryBase>. Сведения о реализации коллекции делегатов не обязательно предоставлять за пределами класса.  
  
 Каждое свойство события внутри класса определяет метод доступа add и remove. Метод доступа add для свойства события добавляет входной экземпляр делегата в коллекцию. Метод доступа remove для свойства события удаляет входной экземпляр делегата из коллекции. Методы доступа к свойствам событий используют предопределенный ключ для свойства события, чтобы добавлять экземпляры в коллекцию делегатов и удалять их из нее.  
  
### <a name="to-handle-multiple-events-using-event-properties"></a>Обработка нескольких событий с помощью их свойств  
  
1. Определите коллекцию делегатов внутри класса, который вызывает события.  
  
2. Определите ключ для каждого события.  
  
3. Определите свойства событий в классе, который вызывает события.  
  
4. Используйте коллекцию делегатов для реализации методов доступа add и remove для свойств событий.  
  
5. Используйте открытые свойства событий делегатов обработчика событий добавления и удаления в классах, обрабатывающих эти события.  
  
## <a name="example"></a>Пример  
 В следующем примере C# реализуются свойства событий `MouseDown` и `MouseUp` с использованием объекта <xref:System.ComponentModel.EventHandlerList> для хранения делегата каждого события. Ключевые слова для конструкции свойств событий выделены жирным шрифтом.  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [События](../../../docs/standard/events/index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [Практическое руководство. Объявление пользовательских событий для экономии памяти](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
