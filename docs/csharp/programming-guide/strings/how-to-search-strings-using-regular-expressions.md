---
title: "Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c851c57b44f1343816b905db002e530121fb6c0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)
Класс <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> можно использовать для поиска строк. Это может быть как простейший, так и полноценный поиск с использованием всех возможностей регулярных выражений. Ниже приведены два примера поиска строк с использованием класса <xref:System.Text.RegularExpressions.Regex>. Дополнительные сведения см. в разделе [Регулярные выражения в .NET Framework](https://msdn.microsoft.com/library/hs600312).  
  
## <a name="example"></a>Пример  
 В следующем коде реализуется консольное приложение, выполняющее простой поиск без учета регистра символов по строкам массива. Статический метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> выполняет поиск заданного шаблона в указанной строке. В этом случае третий аргумент определяет, необходимо ли учитывать регистр символов. Для получения дополнительной информации см. <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем коде реализуется консольное приложение для проверки формата каждой строки в массиве с использованием регулярных выражений. По условиям проверки каждая строка должна иметь формат номера телефона: три группы цифр, разделенных дефисами. Первые две группы содержат по три цифры, и третья группа состоит из четырех цифр. Для этого используется регулярное выражение `^\\d{3}-\\d{3}-\\d{4}$`. Дополнительные сведения см. в разделе [Элементы языка регулярных выражений. Краткий справочник](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).  
  
 [!code-csharp[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Строки](../../../csharp/programming-guide/strings/index.md)  
 [Регулярные выражения в .NET Framework](https://msdn.microsoft.com/library/hs600312)  
 [Элементы языка регулярных выражений — краткий справочник](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)
