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
# <a name="how-to-convert-between-legacy-encodings-and-unicode-c-programming-guide"></a><span data-ttu-id="d0f6d-102">Практическое руководство. Преобразование из устаревших кодировок в Юникод (Руководство по программированию в C#)</span><span class="sxs-lookup"><span data-stu-id="d0f6d-102">How to: Convert Between Legacy Encodings and Unicode (C# Programming Guide)</span></span>
<span data-ttu-id="d0f6d-103">В C# все строки в памяти имеют кодировку Юникод (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="d0f6d-103">In C#, all strings in memory are encoded as Unicode (UTF-16).</span></span> <span data-ttu-id="d0f6d-104">При извлечении данных из хранилища в объект `string` они автоматически преобразуются в формат UTF-16.</span><span class="sxs-lookup"><span data-stu-id="d0f6d-104">When you bring data from storage into a `string` object, the data is automatically converted to UTF-16.</span></span> <span data-ttu-id="d0f6d-105">Если данные содержат только ASCII-символы со значениями от 0 до 127, для преобразования не требуется никаких дополнительных действий с вашей стороны.</span><span class="sxs-lookup"><span data-stu-id="d0f6d-105">If the data contains only ASCII values from 0 through 127, the conversion requires no extra effort on your part.</span></span> <span data-ttu-id="d0f6d-106">Тем не менее, если исходный текст содержит дополнительные байтовые значения ASCII (от 128 до 255), символы расширенного набора по умолчанию будут интерпретироваться в соответствии с текущей кодовой страницей.</span><span class="sxs-lookup"><span data-stu-id="d0f6d-106">However, if the source text contains extended ASCII byte values (128 through 255), the extended characters will be interpreted by default according to the current code page.</span></span> <span data-ttu-id="d0f6d-107">Чтобы указать способ интерпретации исходного текста в соответствии с кодовой страницей, используйте класс <xref:System.Text.Encoding?displayProperty=fullName>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d0f6d-107">To specify that the source text should be interpreted according to a different code page, use the <xref:System.Text.Encoding?displayProperty=fullName> class as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0f6d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d0f6d-108">Example</span></span>  
 <span data-ttu-id="d0f6d-109">В следующем примере демонстрируется преобразование текстового файла в 8-битной кодировке ASCII с интерпретацией исходного текста в соответствии с кодовой страницей Windows 737.</span><span class="sxs-lookup"><span data-stu-id="d0f6d-109">The following example shows how to convert a text file that has been encoded in 8-bit ASCII, interpreting the source text according to Windows Code Page 737.</span></span>  
  
 <span data-ttu-id="d0f6d-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d0f6d-110">[!code-cs[csProgGuideStrings#34](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-convert-between-legacy-encodings-and-unicode_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f6d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d0f6d-111">See Also</span></span>  
 [<span data-ttu-id="d0f6d-112">Строки</span><span class="sxs-lookup"><span data-stu-id="d0f6d-112">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)

