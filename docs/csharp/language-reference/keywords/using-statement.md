---
title: "Оператор using (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
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
ms.openlocfilehash: 587e50d5c81c19d75e9d8bf4779064947a373b71
ms.lasthandoff: 03/13/2017

---
# <a name="using-statement-c-reference"></a>Оператор using (Справочник по C#)
Предоставляет удобный синтаксис, обеспечивающий правильное использование объектов <xref:System.IDisposable>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как использовать оператор using.  
  
 [!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a>Примечания  
 <xref:System.IO.File> и <xref:System.Drawing.Font> представляют собой примеры управляемых типов, которые обращаются к неуправляемым ресурсам (в данном случае это обработчики файлов и контексты устройств). Существуют и многие другие виды неуправляемых ресурсов и типов библиотек классов, которые их инкапсулируют. Все эти типы должны реализовывать интерфейс <xref:System.IDisposable>.  
  
 Как правило, при использовании объекта `IDisposable` его следует объявить в операторе `using` и создать в нем его экземпляр. Оператор `using` правильно вызывает метод <xref:System.IDisposable.Dispose%2A> для объектов, а также (если он используется, как показано выше) становится причиной выхода объекта из области действия, как только вызывается метод <xref:System.IDisposable.Dispose%2A>. В блоке `using` объект доступен только для чтения, и изменить или переназначить его нельзя.  
  
 Оператор `using` обеспечивает вызов метода <xref:System.IDisposable.Dispose%2A>, даже если при вызове методов для соответствующего объекта возникает исключение. Тот же результат можно получить, поместив объект в блок try, а затем вызвав метод <xref:System.IDisposable.Dispose%2A> в блоке finally; фактически компилятор переводит оператор `using` именно так. Во время компиляции представленный выше код разворачивается в следующий (обратите внимание на дополнительные фигурные скобки, создающие ограниченную область действия для объекта):  
  
 [!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 В операторе `using` можно объявить сразу несколько экземпляров типа, как показано в следующем примере.  
  
 [!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 Вы можете создать экземпляр объекта ресурсов, а затем передать переменную в оператор `using`, однако делать этого не рекомендуется. В этом случае объект остается в области действия и после того, как блок `using` теряет контроль, несмотря на то, что доступа к неуправляемым ресурсам у него, скорее всего, не будет. Другими словами, он больше не будет полностью инициализирован. При попытке использовать объект за пределами блока `using` может возникнуть исключение. По этой причине лучше создать экземпляр объекта в операторе `using` и ограничить область действия блоком `using`.  
  
 [!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Директива using](../../../csharp/language-reference/keywords/using-directive.md)   
 [Сборка мусора](../../../standard/garbagecollection/index.md)   
 [Реализация метода dispose](http://msdn.microsoft.com/library/eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9)
