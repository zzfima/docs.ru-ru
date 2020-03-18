---
title: '#elif. Справочник по C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: c78818f40b76414d289af6c704ff019b63befe37
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712576"
---
# <a name="elif-c-reference"></a>#elif (Справочник по C#)
Директива `#elif` позволяет создать составную условную директиву. Выражение `#elif` будет вычисляться в том случае, если ни одна из предшествующих директив [#if](./preprocessor-if.md) или необязательных директив `#elif` после вычисления выражения не возвращает значение `true`. Если после вычисления выражения `#elif` возвращается значение `true`, компилятор вычисляет весь код между директивой `#elif` и следующей условной директивой. Пример:  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 Для вычисления нескольких символов можно использовать операторы `==` (равенство), `!=` (неравенство), `&&` (И) и `||` (ИЛИ). Можно также группировать символы и операторы при помощи скобок.  
  
## <a name="remarks"></a>Remarks  
 Применение `#elif` эквивалентно следующему:  
  
```csharp
#else  
#if  
```  
  
 Директива `#elif` позволяет упростить код, поскольку для каждой директивы `#if` требуется отдельная директива [#endif](./preprocessor-endif.md), тогда как `#elif` можно использовать без соответствующей директивы `#endif`.  
  
 В разделе [#if](./preprocessor-if.md) приводится пример использования директивы `#elif`.  
  
## <a name="see-also"></a>См. также раздел

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Директивы препроцессора C#](./index.md)
