---
title: object (справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: 67eaf7f1fd2f01e433395ed21701c3b7fad7c7b4
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199255"
---
# <a name="object-c-reference"></a>object (справочник по C#)
Тип `object` — это псевдоним для <xref:System.Object> в .NET Framework. В унифицированной системе типов C# все типы, стандартные и определяемые пользователем, ссылочные типы и типы значений напрямую или косвенно наследуются из <xref:System.Object>. Переменным типа `object` можно назначать значения любого типа. Если переменная типа значения преобразуется в объект, она считается *упакованной*. Если переменная типа значения преобразуется в тип значения, она считается *распакованной*. Дополнительные сведения см. в разделе [Упаковка-преобразование и распаковка-преобразование](../../../csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как переменные типа `object` могут принимать значения любого типа данных и как переменные типа `object` могут применять методы к <xref:System.Object> из платформы .NET Framework.  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Ссылочные типы](../../../csharp/language-reference/keywords/reference-types.md)  
 [Типы значений](../../../csharp/language-reference/keywords/value-types.md)
