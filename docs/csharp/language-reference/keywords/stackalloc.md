---
title: "stackalloc (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
dev_langs:
- CSharp
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
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
ms.openlocfilehash: 53d61cfdcf4d356a28881c57ad923017c2b479ae
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

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
 [!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
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

