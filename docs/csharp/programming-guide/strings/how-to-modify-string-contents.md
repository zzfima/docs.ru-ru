---
title: "Практическое руководство. Изменение содержимого строки (Руководство по программированию в C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- strings [C#], modifying
ms.assetid: b6c20bba-ce22-43d7-ad1b-5ce65f714055
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b0810d5722c2c32f7884187bb2e3fc5a039825c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-string-contents-c-programming-guide"></a>Практическое руководство. Изменение содержимого строки (Руководство по программированию в C#)
Поскольку строки являются *неизменяемыми*, после создания строкового объекта нельзя изменить его значение без использования небезопасного кода. Тем не менее есть множество способов изменить значение строки и сохранить результат в новом строковом объекте. В классе <xref:System.String?displayProperty=nameWithType> представлены методы, которые позволяют работать с входной строкой и вернуть новый строковый объект. Во многих случаях новый объект можно присвоить переменной, содержащей исходную строку. Класс <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType> предоставляет дополнительные методы, работающие аналогичным образом. Класс <xref:System.Text.StringBuilder?displayProperty=nameWithType> предоставляет буфер символов, который можно изменять на месте. При вызове метода <xref:System.Text.StringBuilder.ToString%2A?displayProperty=nameWithType> создается новый строковый объект, в который помещается текущее содержимое буфера.  
  
## <a name="example"></a>Пример  
 В следующем примере показаны различные способы замены или удаления подстрок в указанной строке.  
  
 [!code-csharp[csProgGuideStrings#28](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_1.cs)]  
  
## <a name="example"></a>Пример  
 Для доступа к отдельным символам строки с применением нотации массива можно использовать объект <xref:System.Text.StringBuilder>, который перегружает оператор `[]` для доступа к его внутреннему буферу символов. Также можно преобразовать строку в массив символов с помощью метода <xref:System.String.ToCharArray%2A>. В следующем примере с помощью метода `ToCharArray` создается массив. После этого некоторые элементы массива изменяются. Затем вызывается конструктор строки, который принимает в качестве входного параметра массив символов и создает новую строку.  
  
 [!code-csharp[csProgGuideStrings#24](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_2.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере показана редкая ситуация, в которой требуется изменить строку на месте с использованием небезопасного кода аналогично массивам символов в языке C. В этом примере демонстрируется доступ к отдельным символам на месте с помощью ключевого слова fixed. Также здесь показан один из возможных побочных эффектов, связанных с выполнением небезопасных операций со строками, причиной которого является интернирование (внутреннее сохранение) строк компилятором C#. В общем случае этот способ следует использовать только при крайней необходимости.  
  
 [!code-csharp[csProgGuideStrings#29](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-modify-string-contents_3.cs)]  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Строки](../../../csharp/programming-guide/strings/index.md)
