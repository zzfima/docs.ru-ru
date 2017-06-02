---
title: "?? Оператор . (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ??_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: de2abc6830419c368c6a62dfd74fc6f2013db9d4
ms.contentlocale: ru-ru
ms.lasthandoff: 05/22/2017

---
# <a name="-operator-c-reference"></a>?? Оператор (ссылка C#)
Оператор `??` называется оператором объединения со значением NULL.  Он возвращает левый операнд, если этот операнд не имеет значение NULL; в противном случае возвращается правый операнд.  
  
## <a name="remarks"></a>Примечания  
 Тип, допускающий значение NULL, может представлять значение из домена типа или иметь неопределенное значение (в последнем случае значение равно NULL). Синтаксические возможности оператора `??` можно использовать для возврата соответствующего значения (правого операнда), если тип левого операнда допускает значение NULL и левый операнд имеет значение NULL. Если без использования оператора `??` попытаться присвоить тип, допускающий значение NULL, типу, не допускающему такое значение, то во время компиляции появится ошибка. Если используется приведение типов и допускающий значение NULL тип в данный момент не определен, будет создано исключение `InvalidOperationException`.  
  
 Дополнительные сведения см. в разделе [Nullable Types](../../../csharp/programming-guide/nullable-types/index.md) (Типы, допускающие значение NULL).  
  
 Результат ?? Оператор не считается константой, даже если оба его аргумента являются константами.  
  
## <a name="example"></a>Пример  
 [!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Операторы в C#](../../../csharp/language-reference/operators/index.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Что означает термин "расширенные"?](http://go.microsoft.com/fwlink/?LinkID=112382)
