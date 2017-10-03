---
title: "delegate (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- delegate_CSharpKeyword
- delegate
- CS0123
dev_langs:
- CSharp
helpviewer_keywords:
- delegate keyword [C#]
- function pointers [C#]
ms.assetid: 0bb8cb6d-2f87-47c7-9d1f-d65c1cd01e9f
caps.latest.revision: 24
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 402eedd0c59b5c95e1a9b44faca66ccb4d4e04e7
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="delegate-c-reference"></a>delegate (Справочник по C#)
Объявление типа делегата аналогично сигнатуре метода. Оно имеет возвращаемое значение и любое число параметров любого типа:  
  
```  
public delegate void TestDelegate(string message);  
public delegate int TestDelegate(MyType m, long num);  
```  
  
 Ключевое слово `delegate` имеет ссылочный тип, который можно использовать для инкапсуляции именованного или анонимного метода. Делегаты аналогичны используемым в языке C++ указателям функций, но являются типобезопасными и безопасными. Сведения о применении делегатов см. в разделах [Делегаты](../../../csharp/programming-guide/delegates/index.md) и [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md).  
  
## <a name="remarks"></a>Примечания  
 Делегаты являются основой [событий](../../../csharp/programming-guide/events/index.md).  
  
 Экземпляры делегата могут создаваться путем его связывания с именованным или анонимным методом. Дополнительные сведения см. в разделах [Именованные методы](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md) и [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).  
  
 Делегат должен быть создан при помощи метода или лямбда-выражения, имеющего совместимые возвращаемый тип и входные параметры. Дополнительные сведения о допустимой степени вариации сигнатур методов см. в разделе [Вариативность в делегатах](http://msdn.microsoft.com/library/e3b98197-6c5b-4e55-9c6e-9739b60645ca). Для использования с анонимными методами делегат и код, который должен быть связан с ним, должны быть объявлены вместе. В этом разделе рассматриваются оба способа создания экземпляров делегатов.  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsTypes#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/delegate_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)   
 [Делегаты](../../../csharp/programming-guide/delegates/index.md)   
 [События](../../../csharp/programming-guide/events/index.md)   
 [Делегаты с именованными методами и Делегаты с анонимными методами](../../../csharp/programming-guide/delegates/delegates-with-named-vs-anonymous-methods.md)   
 [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)

