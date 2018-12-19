---
title: '* Оператор. Справочник по C#'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 24ac4a99c48f1e8204b821bfbf5f7fbc0a2b2f1d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237354"
---
# <a name="-operator-c-reference"></a>Оператор * (Справочник по C#)
Оператор умножения (`*`) вычисляет произведение операндов. Все числовые типы имеют предопределенные операторы умножения.  

Кроме того, `*` служит оператором разыменования, позволяющим выполнять чтение указателя и запись в него.
  
## <a name="remarks"></a>Примечания  
 Оператор `*` также используется для объявления типов указателей и для разыменования указателей. Этот оператор может использоваться только в небезопасных контекстах, обозначенных с помощью ключевого слова [unsafe](../../../csharp/language-reference/keywords/unsafe.md) и требующих параметр компилятора [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  Оператор разыменования также известен как оператор косвенного обращения.  
  
 Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `*` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.  
  
## <a name="example"></a>Пример  
 [!code-csharp-interactive[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)
