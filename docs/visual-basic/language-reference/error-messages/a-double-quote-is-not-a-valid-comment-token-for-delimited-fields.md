---
title: Двойные кавычки не являются допустимой лексемой комментария для полей с разделителями, где EscapeQuote имеет значение True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_InvalidComment
ms.assetid: 636d4b81-00ba-4cfd-98f7-4d57036f494d
ms.openlocfilehash: b49a3223c6638adff757d7d82aee549cb1fee473
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64646930"
---
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a><span data-ttu-id="19d2e-102">Двойные кавычки не являются допустимой лексемой комментария для полей с разделителями, где EscapeQuote имеет значение True</span><span class="sxs-lookup"><span data-stu-id="19d2e-102">A double quote is not a valid comment token for delimited fields where EscapeQuote is set to True</span></span>
<span data-ttu-id="19d2e-103">Введен знак кавычек в качестве разделителя для `TextFieldParser`, но `EscapeQuotes` имеет значение `True`.</span><span class="sxs-lookup"><span data-stu-id="19d2e-103">A quotation mark has been supplied as the delimiter for the `TextFieldParser`, but `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="19d2e-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="19d2e-104">To correct this error</span></span>  
  
- <span data-ttu-id="19d2e-105">Присвойте свойству `EscapeQuotes` значение `False`.</span><span class="sxs-lookup"><span data-stu-id="19d2e-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d2e-106">См. также</span><span class="sxs-lookup"><span data-stu-id="19d2e-106">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [<span data-ttu-id="19d2e-107">Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми</span><span class="sxs-lookup"><span data-stu-id="19d2e-107">How to: Read From Comma-Delimited Text Files</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
