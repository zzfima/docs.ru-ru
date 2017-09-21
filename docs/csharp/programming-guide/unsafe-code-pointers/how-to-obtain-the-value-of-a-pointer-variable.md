---
title: "Практическое руководство. Получение значения переменной указателя (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
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
ms.openlocfilehash: 4cff42de07f2edb279ddd1cafefe9f4b67a38ce1
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>Практическое руководство. Получение значения переменной указателя (Руководство по программированию в C#)
Оператор косвенного обращения к указателю позволяет получить переменную в расположении, на которое указывает указатель. Выражение имеет следующую форму, где `p` — это тип указателя:  
  
```  
*p;  
```  
  
 Унарный оператор косвенного обращения можно использовать только по отношению к выражениям с типом указателя. Кроме того, его нельзя применять к указателю [void](../../../csharp/language-reference/keywords/void.md).  
  
 Если оператор косвенного обращения применяется к указателю [NULL](../../../csharp/language-reference/keywords/null.md), результат будет зависеть от особенностей реализации.  
  
## <a name="example"></a>Пример  
 В следующем примере доступ к переменной типа `char` осуществляется с использованием указателей разных типов. Обратите внимание, что адрес `theChar` может изменяться с каждым запуском из-за изменения физического адреса переменной.  
  
 [!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
 **Значение theChar = Z**   
**Адрес theChar = 12F718**  
**Значение pChar = Z**   
**Значение pInt = 90**    
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Типы](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)

