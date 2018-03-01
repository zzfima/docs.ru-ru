---
title: "Оператор ^ (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4ccd32ea8abd8ca3252380083eafecad2b572ed7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
