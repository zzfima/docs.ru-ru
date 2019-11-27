---
title: Практическое руководство. Преобразование шестнадцатеричных строк в числа
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347176"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Практическое руководство. Преобразование шестнадцатеричных строк в числа (Visual Basic)

В этом примере шестнадцатеричная строка преобразуется в целое число с помощью метода <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>.

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Преобразование шестнадцатеричной строки в число

- Используйте метод <xref:System.Convert.ToInt32(System.String,System.Int32)> для преобразования числа, выраженного в кодировке base-16, в целое число.

  Первым аргументом метода <xref:System.Convert.ToInt32(System.String,System.Int32)> является Преобразуемая строка. Второй аргумент описывает, в какой базе чисел выражается число. шестнадцатеричное число — основание 16.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- Обратите внимание, что шестнадцатеричная строка имеет следующие ограничения.

  - Он не может включать префикс `&h`.
  - Он не может включать `_` разделитель цифр.

  При наличии префикса или разделителя цифр вызов метода <xref:System.Convert.ToInt32(System.String,System.Int32)> создает <xref:System.FormatException>.

## <a name="see-also"></a>См. также

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
