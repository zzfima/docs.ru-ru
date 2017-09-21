---
title: "Практическое руководство. Преобразование из устаревших кодировок в Юникод (Руководство по программированию в C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], legacy to unicode encoding
- strings [C#], converting between encodings
ms.assetid: 4eed7d8e-47ab-4a7c-8b95-9645a0ef000b
caps.latest.revision: 11
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
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a016f4ab7de25eec408243cb9b467f9255556bba
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a>Практическое руководство. Преобразование из устаревших кодировок в Юникод (Руководство по программированию в C#)
В C# все строки в памяти имеют кодировку Юникод (UTF-16). При извлечении данных из хранилища в объект `string` они автоматически преобразуются в формат UTF-16. Если данные содержат только ASCII-символы со значениями от 0 до 127, для преобразования не требуется никаких дополнительных действий с вашей стороны. Тем не менее, если исходный текст содержит дополнительные байтовые значения ASCII (от 128 до 255), символы расширенного набора по умолчанию будут интерпретироваться в соответствии с текущей кодовой страницей. Чтобы указать способ интерпретации исходного текста в соответствии с кодовой страницей, используйте класс <xref:System.Text.Encoding?displayProperty=fullName>, как показано в следующем примере.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется преобразование текстового файла в 8-битной кодировке ASCII с интерпретацией исходного текста в соответствии с кодовой страницей Windows 737.  
  
 [!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]  
  
## <a name="see-also"></a>См. также  
 [Строки](../../../csharp/programming-guide/strings/index.md)

