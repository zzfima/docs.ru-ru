---
title: Руководство по программированию на C#. Передача параметров типа значения
ms.date: 07/20/2015
helpviewer_keywords:
- method parameters [C#], value types
- parameters [C#], value
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
ms.openlocfilehash: b6999c90bbe254542419232ab719a2754018d295
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705461"
---
# <a name="passing-value-type-parameters-c-programming-guide"></a>Передача параметров типа значения (Руководство по программированию в C#)
Переменная [типа значения](../../language-reference/keywords/value-types.md) напрямую содержит данные, в отличие от переменной [ссылочного типа](../../language-reference/keywords/reference-types.md), которая содержит только ссылку на данные. Передавая в метод переменную типа значения, вы передаете ему копию этой переменной. Любые изменения параметра, которые происходят внутри метода, не влияют на исходные данные, хранимые в переменной. Если вы хотите, чтобы вызываемый метод изменял значение аргумента, его необходимо передать по ссылке с помощью ключевых слов [ref](../../language-reference/keywords/ref.md) или [out](../../language-reference/keywords/out-parameter-modifier.md). Можно также использовать ключевое слово [in](../../language-reference/keywords/in-parameter-modifier.md) для передачи параметра значения по ссылке, чтобы избежать копирования и гарантировать неизменность значения. В следующих примерах мы для простоты используем `ref`.  
  
## <a name="passing-value-types-by-value"></a>Передача переменных типа значения по значению  
 Следующий пример демонстрирует передачу параметров типа значения по значению. Переменная `n` передается по значению в метод `SquareIt`. Любые изменения, выполненные внутри метода, не влияют на исходное значение переменной.  
  
 [!code-csharp[csProgGuideParameters#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#3)]  
  
 Переменная `n` имеет тип значения. Она содержит данные, в нашем примере это значение `5`. Когда вызывается `SquareIt`, содержимое `n` копируется в параметр `x`, который используется исключительно внутри метода. Но в `Main` значение `n` всегда останется прежним после выполнения метода `SquareIt`. Изменения, выполненные внутри метода, влияют только на локальную переменную `x`.  
  
## <a name="passing-value-types-by-reference"></a>Передача переменных типа значения по ссылке  
 Следующий пример полностью совпадает с предыдущим, но теперь аргумент передается как параметр `ref`. Значение базового аргумента `n` будет изменяться, когда метод изменяет значение `x`.  
  
 [!code-csharp[csProgGuideParameters#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#4)]  
  
 В этом примере передается не значение `n`, а ссылка на `n`. Теперь параметр `x` будет не значением типа [int](../../language-reference/builtin-types/integral-numeric-types.md), а ссылкой на `int`. В нашем примере это ссылка на `n`. Таким образом, при передаче `x` в метод передается только информация о том, что `x` ссылается на `n`.  
  
## <a name="swapping-value-types"></a>Изменение типов значений  
 Распространенным примером изменения значений аргументов является метод замены, при котором в метод передаются две переменные, а метод меняет местами их содержимое. Для метода замены аргументы необходимо передавать по ссылке. В противном случае замена затронет лишь локальные копии параметров в этом методе, но в вызывающем методе не произойдет никаких изменений. В следующем примере меняются местами целочисленные значения.  
  
 [!code-csharp[csProgGuideParameters#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#5)]  
  
 При вызове метода `SwapByRef` используйте ключевое слово `ref`, как показано в следующем примере.  
  
 [!code-csharp[csProgGuideParameters#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#6)]  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Передача параметров](./passing-parameters.md)
- [Передача параметров ссылочного типа](./passing-reference-type-parameters.md)
