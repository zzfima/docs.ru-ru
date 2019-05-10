---
title: Не удается прочитать поля с разделителями, поскольку двойные кавычки не являются допустимым разделителем, если параметр EscapeQuotes имеет значение True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: ca764d5258daf54a7149661549a78b3aca709718
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619803"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a><span data-ttu-id="b396d-102">Не удается прочитать поля с разделителями, поскольку двойные кавычки не являются допустимым разделителем, если параметр EscapeQuotes имеет значение True</span><span class="sxs-lookup"><span data-stu-id="b396d-102">Unable to read delimited fields because a double quote is not a legal delimiter when EscapeQuotes is set to True</span></span>
<span data-ttu-id="b396d-103">`TextFieldParser` не может читать из файла, поскольку в качестве разделителя указан знак кавычек ("), а `EscapeQuotes` имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="b396d-103">The `TextFieldParser` cannot read from the file because a quotation mark (") has been supplied as the delimiter and `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b396d-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="b396d-104">To correct this error</span></span>  
  
- <span data-ttu-id="b396d-105">Присвойте свойству `EscapeQuotes` значение `False`.</span><span class="sxs-lookup"><span data-stu-id="b396d-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b396d-106">См. также</span><span class="sxs-lookup"><span data-stu-id="b396d-106">See also</span></span>

- [<span data-ttu-id="b396d-107">Метод TextFieldParser.SetDelimiters</span><span class="sxs-lookup"><span data-stu-id="b396d-107">TextFieldParser.SetDelimiters Method</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [<span data-ttu-id="b396d-108">TextFieldParser.Delimiters Property</span><span class="sxs-lookup"><span data-stu-id="b396d-108">TextFieldParser.Delimiters Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [<span data-ttu-id="b396d-109">Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="b396d-109">How to: Read From Comma-Delimited Text Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="b396d-110">Объект TextFieldParser</span><span class="sxs-lookup"><span data-stu-id="b396d-110">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
