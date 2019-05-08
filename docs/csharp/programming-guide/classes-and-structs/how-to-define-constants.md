---
title: Практическое руководство. Определение констант в C#
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: a85e7728512922be38658c07314229c26b2461fd
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201473"
---
# <a name="how-to-define-constants-in-c"></a>Практическое руководство. Определение констант в C\#
Константы — это поля, значения которых устанавливаются во время компиляции и не изменяются. С помощью констант можно присвоить особым значениям значащие имена вместо числовых литералов.  
  
> [!NOTE]
>  В C# с помощью директивы препроцессора [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) нельзя определять константы так, как это было реализовано в C и C++.  
  
 Чтобы определить значения константы целочисленного типа (`int`, `byte` и т. д.), используйте перечисляемый тип. Дополнительные сведения см. в разделе [Перечисление](../../../csharp/language-reference/keywords/enum.md).  
  
 Чтобы определить нецелочисленные константы, можно сгруппировать их в статический класс с именем `Constants`. В этом случае перед любыми ссылками на константы будет необходимо указывать имя класса, как показано в следующем примере.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 Используя квалификатор имени класса, вы гарантируете, что вы сами и другие разработчики будете понимать, что имеете дело с константой, которую нельзя изменить.  
  
## <a name="see-also"></a>См. также

- [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)
