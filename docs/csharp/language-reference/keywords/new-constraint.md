---
title: Ограничение new (Справочник по C#)
ms.date: 07/20/2015
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
ms.openlocfilehash: 77c955102ba9cede831c85838a6a7e57025ad35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269000"
---
# <a name="new-constraint-c-reference"></a>Ограничение new (Справочник по C#)
Ограничение `new` указывает, что аргумент любого типа в объявлении универсального класса должен иметь открытый конструктор без параметров. Использовать ограничение new можно только в том случае, если тип не является абстрактным.  
  
## <a name="example"></a>Пример  
 Примените ограничение `new` к параметру типа, когда общий класс создает новые экземпляры этого типа, как показано в следующем примере:  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a>Пример  
 При использовании ограничения `new()` с другими ограничениями его необходимо указывать последним:  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 Дополнительные сведения см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic>  
 [Справочник по C#](../../../csharp/language-reference/index.md)  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)  
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)
