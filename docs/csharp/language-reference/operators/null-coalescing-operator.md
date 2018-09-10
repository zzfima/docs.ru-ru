---
title: ?? Оператор (ссылка C#)
ms.date: 07/20/2015
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 03d81d4216dabce2ea75b9fdcf6ef0971cc32490
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530110"
---
# <a name="-operator-c-reference"></a>?? Оператор (ссылка C#)
Оператор `??` называется оператором объединения со значением NULL.  Он возвращает левый операнд, если этот операнд не имеет значение NULL; в противном случае возвращается правый операнд.  
  
## <a name="remarks"></a>Примечания  
 Тип, допускающий значение NULL, может представлять значение из домена типа или иметь неопределенное значение (в последнем случае значение равно NULL). Синтаксические возможности оператора `??` можно использовать для возврата соответствующего значения (правого операнда), если тип левого операнда допускает значение NULL и левый операнд имеет значение NULL. Если без использования оператора `??` попытаться присвоить тип, допускающий значение NULL, типу, не допускающему такое значение, то во время компиляции появится ошибка. Если используется приведение типов и допускающий значение NULL тип в данный момент не определен, будет создано исключение `InvalidOperationException`.  
  
 Дополнительные сведения см. в разделе [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Типы, допускающие значение NULL).  
  
 Результат ?? Оператор не считается константой, даже если оба его аргумента являются константами.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a>См. также

- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Операторы в C#](../../../csharp/language-reference/operators/index.md)  
- [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)  
- [Что означает термин "расширенные"?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
