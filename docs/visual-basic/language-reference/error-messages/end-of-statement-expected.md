---
title: Ожидается окончание оператора
ms.date: 07/20/2015
f1_keywords:
- bc30205
- vbc30205
helpviewer_keywords:
- BC30205
ms.assetid: 53c7f825-a737-4b76-a1fa-f67745b8bd40
ms.openlocfilehash: ab6a4a0e6736e2af9c1fa0dd170b6aa4c42d9e4a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817158"
---
# <a name="end-of-statement-expected"></a>Ожидается окончание оператора
Оператор является синтаксически завершенным, однако дополнительный программный элемент элементом, выполненной инструкции. Признак конца строки является обязательным в конце каждой инструкции.
  
 Признак конца строки делит символов файла исходного кода в Visual Basic на строки. Признаки конца строки относятся Юникода каретки возвращаемого символа (& HD), Юникод перевода строки символ (& высокой ДОСТУПНОСТИ), и символ, за которым следует символ перевода строки Юникода возврата каретки Юникода. Дополнительные сведения о признаки конца строки, см. в разделе [спецификация языка Visual Basic](~/_vblang/spec/lexical-grammar.md#line-terminators).
  
 **Идентификатор ошибки:** BC30205
  
## <a name="to-correct-this-error"></a>Исправление ошибки
  
1.  Установите этот флажок, чтобы увидеть, если два отдельных оператора случайно помещенных в той же строке.
  
2.  Вставьте знак завершения строки после элемента, выполняемой инструкции.
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Разбиение и объединение инструкций в коде](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
- [Операторы](../../../visual-basic/programming-guide/language-features/statements.md)
