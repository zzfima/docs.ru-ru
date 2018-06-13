---
title: Ожидается окончание оператора
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: 7b91d13cbcb9d211d4ca18c8e48c7494bf6eccc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588084"
---
# <a name="end-of-statement-expected"></a>Ожидается окончание оператора
Оператор является синтаксически завершенным, однако дополнительный программный элемент элементом, выполненную инструкцию. Признак конца строки является обязательным в конце каждой инструкции.
  
 Признак конца строки делит символы исходным файлом Visual Basic на строки. Признаки конца строки приведены несколько Юникода каретки возвращаемого символа (& HD), Юникод перевода строки символов (& HA), и символ, за которым следует символ перевода строки Юникода возврата каретки Юникода. Дополнительные сведения о признаки конца строки см. в разделе [спецификация языка Visual Basic](../../../visual-basic/reference/language-specification/index.md).
  
 **Идентификатор ошибки:** BC30205
  
## <a name="to-correct-this-error"></a>Исправление ошибки
  
1.  Проверьте, если два разных оператора случайно помещенных в той же строке.
  
2.  Вставьте признак конца строки после элемента, выполняемой инструкции.
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
