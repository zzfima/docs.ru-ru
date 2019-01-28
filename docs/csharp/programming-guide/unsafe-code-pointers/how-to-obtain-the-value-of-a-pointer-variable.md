---
title: Как выполнить Руководство по программированию на C#. Получение значения переменной указателя
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointer expressions [C#], indirection
- pointers [C#], indirection
- variables [C#], pointers
- pointers [C#], * operator
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
ms.openlocfilehash: 5fbc925b6770bc951a0d7ec856898f62c265462e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577158"
---
# <a name="how-to-obtain-the-value-of-a-pointer-variable-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Получение значения переменной указателя
Оператор косвенного обращения к указателю позволяет получить переменную в расположении, на которое указывает указатель. Выражение имеет следующую форму, где `p` — это тип указателя:  
  
```  
*p;  
```  
  
 Унарный оператор косвенного обращения можно использовать только по отношению к выражениям с типом указателя. Кроме того, его нельзя применять к указателю [void](../../../csharp/language-reference/keywords/void.md).  
  
 Если оператор косвенного обращения применяется к указателю [NULL](../../../csharp/language-reference/keywords/null.md), результат будет зависеть от особенностей реализации.  
  
## <a name="example"></a>Пример  
 В следующем примере доступ к переменной типа `char` осуществляется с использованием указателей разных типов. Обратите внимание, что адрес `theChar` может изменяться с каждым запуском из-за изменения физического адреса переменной.  
  
 [!code-csharp[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-obtain-the-value-of-a-pointer-variable_2.cs)]  
  
**Значение theChar = Z**
**Адрес theChar = 12F718**
**Значение pChar = Z**
**Значение pInt = 90**

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)
- [Выражения указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [Типы указателей](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Типы](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
