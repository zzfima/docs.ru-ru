---
title: typeof (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 2493e78fd0782eebee17afd979e1c429339d0a3f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43486809"
---
# <a name="typeof-c-reference"></a>typeof (справочник по C#)
Позволяет получить объект `System.Type` для типа. Выражение `typeof` принимает следующую форму:  
  
```csharp  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a>Примечания  
 Получить тип среды выполнения для выражения можно с помощью метода .NET Framework <xref:System.Object.GetType%2A>, как показано в следующем примере:  
  
```csharp  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 Оператор `typeof` перегрузить нельзя.  
  
 Оператор `typeof` можно также применять к открытым универсальным типам. Типы более чем с одним параметром типа должны иметь соответствующее количество запятых в спецификации. В приведенном ниже примере показано, как определить, является ли тип возвращаемого значения метода универсальным <xref:System.Collections.Generic.IEnumerable%601>. <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> возвращает `null`, если тип возвращаемого значения не является универсальным типом <xref:System.Collections.Generic.IEnumerable%601>.
  
 [!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]   
  
## <a name="example"></a>Пример  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a>Пример  
 В этом примере метод <xref:System.Object.GetType%2A> используется для определения типа, который служит для хранения результатов числового вычисления. Он зависит от требований к хранилищу для полученного числа.  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Type?displayProperty=nameWithType>  
- [Справочник по C#](../../../csharp/language-reference/index.md)  
- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
- [is](../../../csharp/language-reference/keywords/is.md)  
- [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)
