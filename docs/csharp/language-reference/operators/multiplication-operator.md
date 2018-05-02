---
title: '* Оператор (ссылка C#)'
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 07d06d668ba43ebc3f4fae394d7b6641b122f4a6
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a>Оператор * (Справочник по C#)
Оператор умножения (`*`) вычисляет произведение операндов. Все числовые типы имеют предопределенные операторы умножения.  

Кроме того, `*` служит оператором разыменования, позволяющим выполнять чтение указателя и запись в него.
  
## <a name="remarks"></a>Примечания  
 Оператор `*` также используется для объявления типов указателей и для разыменования указателей. Этот оператор может использоваться только в небезопасных контекстах, обозначенных с помощью ключевого слова [unsafe](../../../csharp/language-reference/keywords/unsafe.md) и требующих параметр компилятора [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  Оператор разыменования также известен как оператор косвенного обращения.  
  
 Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `*` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
