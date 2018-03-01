---
title: "stackalloc (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad4453f889a344fcd44dfad44a30fef07380b6a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="stackalloc-c-reference"></a>stackalloc (Справочник по C#)
Ключевое слово `stackalloc` используется в контексте небезопасного кода для выделения блока памяти стеку.  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a>Примечания  
 Это ключевое слово допустимо только в инициализаторах локальных переменных. Следующий код вызывает ошибки компилятора.  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 Поскольку задаются типы указателей, `stackalloc` требует [небезопасного](../../../csharp/language-reference/keywords/unsafe.md) контекста. Дополнительные сведения см. в разделе [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 `stackalloc` действует как [_alloca](/cpp/c-runtime-library/reference/alloca) в библиотеке времени выполнения C.  
  
 Представленный ниже код вычисляет и отображает первые 20 чисел в последовательности Фибоначчи. Каждое из них представляет собой сумму двух предыдущих чисел. В этом коде блок памяти, размер которого позволяет сохранить 20 элементов типа `int`, выделяется не куче, а стеку. Адрес блока хранится в указателе `fib`. Эта память не подвергаются сборке мусора, а значит, ее не нужно закреплять (с помощью атрибута [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)). Время существования блока памяти ограничивается временем существования метода, который его определяет. Освободить эту память прежде, чем метод выдаст результат, невозможно.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a>Безопасность  
 Небезопасный код менее безопасен, чем безопасные аналоги. В то же время при использовании `stackalloc` в среде CLR автоматически включается обнаружение переполнения буфера. Если буфер переполнен, процесс незамедлительно прерывается — это позволяет минимизировать риск исполнения вредоносного кода.  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
