---
title: Практические руководства. Поиск в строке Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: fe9e50dc5458fdf8546094e5f41c2f001f1d2791
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700064"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>Как выполнить поиск в строке (Visual Basic)

В этой статье приведен пример поиска в строке в Visual Basic.

## <a name="example"></a>Пример

В этом примере вызывается метод <xref:System.String.IndexOf%2A> для объекта <xref:System.String>, чтобы сообщить индекс первого вхождения подстроки:

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a>Отказоустойчивость

Метод <xref:System.String.IndexOf%2A> возвращает расположение первого символа в первом вхождении подстроки. Индекс основан на 0, что означает, что первый символ строки имеет индекс 0.

Если <xref:System.String.IndexOf%2A> не находит подстроку, возвращается значение-1.

В методе <xref:System.String.IndexOf%2A> учитывается регистр и используется текущий язык и региональные параметры.

Для оптимального управления ошибками может потребоваться заключить Поиск строки в блок `Try` блока [try... Перехватить... Построение оператора finally](../../../language-reference/statements/try-catch-finally-statement.md) .

## <a name="see-also"></a>См. также

- <xref:System.String.IndexOf%2A>
- [Оператор Try...Catch...Finally](../../../language-reference/statements/try-catch-finally-statement.md)
- [Знакомство со строками в Visual Basic](introduction-to-strings.md)
- [Строки](index.md)
