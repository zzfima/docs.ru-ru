---
title: "Не удается прочитать поля с разделителями, поскольку двойные кавычки не являются допустимым разделителем, если параметр EscapeQuotes имеет значение True"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3644165d0c25189f29f3f878a17b0d9bf4e2623b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a><span data-ttu-id="c30e4-102">Не удается прочитать поля с разделителями, поскольку двойные кавычки не являются допустимым разделителем, если параметр EscapeQuotes имеет значение True</span><span class="sxs-lookup"><span data-stu-id="c30e4-102">Unable to read delimited fields because a double quote is not a legal delimiter when EscapeQuotes is set to True</span></span>
<span data-ttu-id="c30e4-103">`TextFieldParser` не может читать из файла, поскольку в качестве разделителя указан знак кавычек ("), а `EscapeQuotes` имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="c30e4-103">The `TextFieldParser` cannot read from the file because a quotation mark (") has been supplied as the delimiter and `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c30e4-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c30e4-104">To correct this error</span></span>  
  
-   <span data-ttu-id="c30e4-105">Присвойте свойству `EscapeQuotes` значение `False`.</span><span class="sxs-lookup"><span data-stu-id="c30e4-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30e4-106">См. также</span><span class="sxs-lookup"><span data-stu-id="c30e4-106">See Also</span></span>  
 [<span data-ttu-id="c30e4-107">Метод TextFieldParser.SetDelimiters</span><span class="sxs-lookup"><span data-stu-id="c30e4-107">TextFieldParser.SetDelimiters Method</span></span>](http://msdn.microsoft.com/en-us/21fa40ec-5866-4d0e-9fd9-c708a190dcc9)  
 [<span data-ttu-id="c30e4-108">Свойство TextFieldParser.Delimiters</span><span class="sxs-lookup"><span data-stu-id="c30e4-108">TextFieldParser.Delimiters Property</span></span>](http://msdn.microsoft.com/en-us/4eb18f4d-3011-40a9-b668-be93eed0444f)  
 [<span data-ttu-id="c30e4-109">Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="c30e4-109">How to: Read From Comma-Delimited Text Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
 [<span data-ttu-id="c30e4-110">Объект TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="c30e4-110">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
