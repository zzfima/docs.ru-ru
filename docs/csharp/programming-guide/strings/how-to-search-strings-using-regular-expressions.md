---
title: "Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- searching strings [C#]
- strings [C#], searching with RegEx
ms.assetid: dcab2150-a4a2-4fe4-87e3-83b83b58d84a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: fb05d1702c75be8fd224ee0f34d7d8d3fe71f207
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-search-strings-using-regular-expressions-c-programming-guide"></a>Практическое руководство. Поиск строк с помощью регулярных выражений (Руководство по программированию в C#)
Класс <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName> можно использовать для поиска строк. Это может быть как простейший, так и полноценный поиск с использованием всех возможностей регулярных выражений. Ниже приведены два примера поиска строк с использованием класса <xref:System.Text.RegularExpressions.Regex>. Дополнительные сведения см. в разделе [Регулярные выражения в .NET Framework](https://msdn.microsoft.com/library/hs600312).  
  
## <a name="example"></a>Пример  
 В следующем коде реализуется консольное приложение, выполняющее простой поиск без учета регистра символов по строкам массива. Статический метод <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=fullName> выполняет поиск заданного шаблона в указанной строке. В этом случае третий аргумент определяет, необходимо ли учитывать регистр символов. Для получения дополнительной информации см. <xref:System.Text.RegularExpressions.RegexOptions?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideStrings#17](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_1.cs)]  
  
## <a name="example"></a>Пример  
 В следующем коде реализуется консольное приложение для проверки формата каждой строки в массиве с использованием регулярных выражений. По условиям проверки каждая строка должна иметь формат номера телефона: три группы цифр, разделенных дефисами. Первые две группы содержат по три цифры, и третья группа состоит из четырех цифр. Для этого используется регулярное выражение `^\\d{3}-\\d{3}-\\d{4}$`. Дополнительные сведения см. в разделе [Элементы языка регулярных выражений. Краткий справочник](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c).  
  
 [!code-cs[csProgGuideStrings#18](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-search-strings-using-regular-expressions_2.cs)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Text.RegularExpressions.Regex?displayProperty=fullName>   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Строки](../../../csharp/programming-guide/strings/index.md)   
 [Регулярные выражения в .NET Framework](https://msdn.microsoft.com/library/hs600312)   
 [Элементы языка регулярных выражений — краткий справочник](http://msdn.microsoft.com/library/930653a6-95d2-4697-9d5a-52d11bb6fd4c)

