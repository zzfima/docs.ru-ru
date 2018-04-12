---
title: Ожидается окончание оператора
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4934952015cb4871bcd90cef982eab5425b1617f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
