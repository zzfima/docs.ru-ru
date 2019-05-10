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
# <a name="a-double-quote-is-not-a-valid-comment-token-for-delimited-fields-where-escapequote-is-set-to-true"></a>Двойные кавычки не являются допустимой лексемой комментария для полей с разделителями, где EscapeQuote имеет значение True
Введен знак кавычек в качестве разделителя для `TextFieldParser`, но `EscapeQuotes` имеет значение `True`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Присвойте свойству `EscapeQuotes` значение `False`.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser>
- [Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
