---
title: "typeof (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
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
ms.sourcegitcommit: 81117b1419c2a9c3babd6a7429052e2b23e08a70
ms.openlocfilehash: 9d56ab9afcac6a27a382f27d853dda58c50f8f01
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="typeof-c-reference"></a>typeof (справочник по C#)
Позволяет получить объект `System.Type` для типа. Выражение `typeof` принимает следующую форму:  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a>Примечания  
 Получить тип среды выполнения для выражения можно с помощью метода .NET Framework <xref:System.Object.GetType%2A>, как показано в следующем примере:  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 Оператор `typeof` перегрузить нельзя.  
  
 Оператор `typeof` можно также применять к открытым универсальным типам. Типы более чем с одним параметром типа должны иметь соответствующее количество запятых в спецификации. В приведенном ниже примере показано, как определить, является ли тип возвращаемого значения метода универсальным <xref:System.Collections.Generic.IEnumerable%601>. Предположим, что метод является экземпляром типа MethodInfo:  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a>Пример  
 [!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере метод <xref:System.Object.GetType%2A> используется для определения типа, который служит для хранения результатов числового вычисления. Он зависит от требований к хранилищу для полученного числа.  
  
 [!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Type?displayProperty=nameWithType>   
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [is](../../../csharp/language-reference/keywords/is.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)

