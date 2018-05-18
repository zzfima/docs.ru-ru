---
title: Оператор ^ (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: 5cc3cd2cfc932646e5b2dd6ec034555b07582379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>Оператор ^ (Справочник по C#)
Бинарные операторы `^` предварительно определены для целочисленных типов и типа `bool`. Для целочисленных типов оператор `^` выполняет побитовую операцию исключающего ИЛИ для всех своих операндов. Для операндов типа `bool` оператор `^` выполняет логическую операцию исключающего ИЛИ для всех своих операндов. Таким образом, значение `true` возвращается только тогда, когда только один из операндов имеет значение `true`.  
  
## <a name="remarks"></a>Примечания  
 Определяемые пользователем типы могут вызвать перегрузку оператора `^` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . Операции с целыми типами обычно разрешены и для перечислений.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 При вычислении выражения `0xf8 ^ 0x3f` в предыдущем примере выполняется побитовая операция исключающего ИЛИ со следующими двумя двоичными значениями, которые соответствуют шестнадцатеричным значениям F8 и 3F:  
  
 `1111 1000`  
  
 `0011 1111`  
  
 В результате выполнения операции исключающего ИЛИ получается значение `1100 0111` или C7 в шестнадцатеричном формате.  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
