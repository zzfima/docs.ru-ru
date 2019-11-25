---
title: Двойные кавычки не являются допустимой лексемой комментария для полей с разделителями, где EscapeQuote имеет значение True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: df7868c510eaacbad1d4421259234f4187f60cd7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976222"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a><span data-ttu-id="101b3-102">Двойные кавычки не являются допустимой лексемой комментария для полей с разделителями, где EscapeQuote имеет значение True</span><span class="sxs-lookup"><span data-stu-id="101b3-102">A double quote is not a valid comment token for delimited fields where EscapeQuote is set to True</span></span>

<span data-ttu-id="101b3-103">Введен знак кавычек в качестве разделителя для `TextFieldParser`, но `EscapeQuotes` имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="101b3-103">A quotation mark has been supplied as the delimiter for the `TextFieldParser`, but `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="101b3-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="101b3-104">To correct this error</span></span>  
  
- <span data-ttu-id="101b3-105">Присвойте свойству `EscapeQuotes` значение `False`.</span><span class="sxs-lookup"><span data-stu-id="101b3-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="101b3-106">См. также</span><span class="sxs-lookup"><span data-stu-id="101b3-106">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [<span data-ttu-id="101b3-107">Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="101b3-107">How to: Read From Comma-Delimited Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
