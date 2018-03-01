---
title: "Оператор using (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fdf37e1bfc57bf850b332f167e57d3e05d23e78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-c-reference"></a>Оператор using (Справочник по C#)
Предоставляет удобный синтаксис, обеспечивающий правильное использование объектов <xref:System.IDisposable>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать оператор using.  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a>Примечания  
 <xref:System.IO.File> и <xref:System.Drawing.Font> представляют собой примеры управляемых типов, которые обращаются к неуправляемым ресурсам (в данном случае это обработчики файлов и контексты устройств). Существуют и многие другие виды неуправляемых ресурсов и типов библиотек классов, которые их инкапсулируют. Все эти типы реализуют интерфейс <xref:System.IDisposable>.  
  
Когда время существования `IDisposable` объекта только один метод, необходимо объявить и создать его в экземпляр `using` инструкции. Оператор `using` правильно вызывает метод <xref:System.IDisposable.Dispose%2A> для объектов, а также (если он используется, как показано выше) становится причиной выхода объекта из области действия, как только вызывается метод <xref:System.IDisposable.Dispose%2A>. В блоке `using` объект доступен только для чтения, и изменить или переназначить его нельзя.  
  
 Оператор `using` обеспечивает вызов метода <xref:System.IDisposable.Dispose%2A>, даже если при вызове методов для соответствующего объекта возникает исключение. Тот же результат можно получить, поместив объект в блок try, а затем вызвав метод <xref:System.IDisposable.Dispose%2A> в блоке finally; фактически компилятор переводит оператор `using` именно так. Во время компиляции представленный выше код разворачивается в следующий (обратите внимание на дополнительные фигурные скобки, создающие ограниченную область действия для объекта):  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 В операторе `using` можно объявить сразу несколько экземпляров типа, как показано в следующем примере.  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 Вы можете создать экземпляр объекта ресурсов, а затем передать переменную в оператор `using`, однако делать этого не рекомендуется. В этом случае объект остается в области действия и после того, как блок `using` теряет контроль, несмотря на то, что доступа к неуправляемым ресурсам у него, скорее всего, не будет. Другими словами, он больше не будет полностью инициализирован. При попытке использовать объект за пределами блока `using` может возникнуть исключение. По этой причине лучше создать экземпляр объекта в операторе `using` и ограничить область действия блоком `using`.  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
Дополнительные сведения об утилизации `IDisposable` объектов, в разделе [с помощью объектов, реализующих IDisposable](../../../standard/garbage-collection/using-objects.md).

## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Директива using](../../../csharp/language-reference/keywords/using-directive.md)  
 [Сборка мусора](../../../standard/garbage-collection/index.md)  
 [Использование объектов, реализующих IDisposable](../../../standard/garbage-collection/using-objects.md)  
 [Интерфейс IDisposable](xref:System.IDisposable)
