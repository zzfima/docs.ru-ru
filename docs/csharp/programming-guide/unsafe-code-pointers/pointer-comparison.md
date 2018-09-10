---
title: Сравнение указателей (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: fa980c944159c477c333762ffad569332fba9402
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086643"
---
# <a name="pointer-comparison-c-programming-guide"></a>Сравнение указателей (Руководство по программированию в C#)
Для сравнения указателей любого типа можно применять следующие операторы:  
  
 **==   !=   \<   >   \<=   >=**  
  
 Операторы сравнения сравнивают адреса двух операндов, принимая их как целые числа без знака.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a>Пример результатов выполнения  
 `True`  
  
 `False`  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
- [Обработка указателей](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [Типы](../../../csharp/language-reference/keywords/types.md)  
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
- [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
