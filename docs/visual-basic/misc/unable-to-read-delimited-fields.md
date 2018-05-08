---
title: Не удается прочитать поля с разделителями, поскольку двойные кавычки не являются допустимым разделителем, если параметр EscapeQuotes имеет значение True
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: 66116e6f3d8338db3884cd375aeb880930c8d861
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>Не удается прочитать поля с разделителями, поскольку двойные кавычки не являются допустимым разделителем, если параметр EscapeQuotes имеет значение True
`TextFieldParser` не может читать из файла, поскольку в качестве разделителя указан знак кавычек ("), а `EscapeQuotes` имеет значение `True`.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Присвойте свойству `EscapeQuotes` значение `False`.  
  
## <a name="see-also"></a>См. также  
 [Метод TextFieldParser.SetDelimiters](http://msdn.microsoft.com/library/21fa40ec-5866-4d0e-9fd9-c708a190dcc9)  
 [Свойство TextFieldParser.Delimiters](http://msdn.microsoft.com/library/4eb18f4d-3011-40a9-b668-be93eed0444f)  
 [Практическое руководство. Чтение из текстовых файлов с разделителями-запятыми](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)  
 [Объект TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
