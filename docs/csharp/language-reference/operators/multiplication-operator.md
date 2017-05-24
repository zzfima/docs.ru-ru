---
title: "* Оператор . (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: 14
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: 7b25091b422de68391b925b492ca1e4cef720467
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="-operator-c-reference"></a>Оператор * (Справочник по C#)
Оператор умножения (`*`), который вычисляет произведение двух операндов.  Кроме того, это оператор разыменования, позволяющий выполнять чтение и запись в указателе.  
  
## <a name="remarks"></a>Примечания  
 Все числовые типы имеют предопределенные операторы умножения.  
  
 Оператор `*` также используется для объявления типов указателей и для разыменования указателей. Этот оператор может использоваться только в небезопасных контекстах, обозначенных с помощью ключевого слова [unsafe](../../../csharp/language-reference/keywords/unsafe.md) и требующих параметр компилятора [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).  Оператор разыменования также известен как оператор косвенного обращения.  
  
 Определяемые пользователем типы могут вызвать перегрузку бинарного оператора `*` (см. раздел [operator](../../../csharp/language-reference/keywords/operator.md)) . При перегрузке бинарного оператора соответствующий оператор присвоения (если таковой имеется) также неявно перегружается.  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Небезопасный код и указатели](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)
