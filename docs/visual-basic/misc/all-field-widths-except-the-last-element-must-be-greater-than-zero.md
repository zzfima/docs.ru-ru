---
title: Все поля, за исключением последнего элемента, должны иметь ширину больше нуля
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: c1537133300ac4de33d0d7ebc3ea0ad6768e8ec9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609149"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a>Все поля, за исключением последнего элемента, должны иметь ширину больше нуля
Все поля, за исключением последнего элемента, должны иметь ширину больше нуля. Ширина поля, меньшая или равная нулю в последнем элементе, указывает, что поле имеет переменную длину.  
  
 Операция не была выполнена, так как ширина поля, отличного от последнего элемента, задана равной нулю или меньше. Ширина поля, меньшая или равная нулю, может использоваться в последнем элементе для указания на то, что последнее поле имеет переменную длину, но не может использоваться как любой другой элемент.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Задайте для ширины поля корректное значение.  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [Практическое руководство. Чтение из текстовых файлов с полями фиксированного размера](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [Объект TextFieldParser](../../visual-basic/language-reference/objects/textfieldparser-object.md)
