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
# <a name="how-to-search-within-a-string-visual-basic"></a><span data-ttu-id="93899-102">Как выполнить поиск в строке (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93899-102">How to: search within a string (Visual Basic)</span></span>

<span data-ttu-id="93899-103">В этой статье приведен пример поиска в строке в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="93899-103">This article shows an example of how to search within a string in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="93899-104">Пример</span><span class="sxs-lookup"><span data-stu-id="93899-104">Example</span></span>

<span data-ttu-id="93899-105">В этом примере вызывается метод <xref:System.String.IndexOf%2A> для объекта <xref:System.String>, чтобы сообщить индекс первого вхождения подстроки:</span><span class="sxs-lookup"><span data-stu-id="93899-105">This example calls the <xref:System.String.IndexOf%2A> method on a <xref:System.String> object to report the index of the first occurrence of a substring:</span></span>

 [!code-vb[VbVbalrStrings#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#71)]

## <a name="robust-programming"></a><span data-ttu-id="93899-106">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="93899-106">Robust programming</span></span>

<span data-ttu-id="93899-107">Метод <xref:System.String.IndexOf%2A> возвращает расположение первого символа в первом вхождении подстроки.</span><span class="sxs-lookup"><span data-stu-id="93899-107">The <xref:System.String.IndexOf%2A> method returns the location of the first character of the first occurrence of the substring.</span></span> <span data-ttu-id="93899-108">Индекс основан на 0, что означает, что первый символ строки имеет индекс 0.</span><span class="sxs-lookup"><span data-stu-id="93899-108">The index is 0-based, which means the first character of a string has an index of 0.</span></span>

<span data-ttu-id="93899-109">Если <xref:System.String.IndexOf%2A> не находит подстроку, возвращается значение-1.</span><span class="sxs-lookup"><span data-stu-id="93899-109">If <xref:System.String.IndexOf%2A> does not find the substring, it returns -1.</span></span>

<span data-ttu-id="93899-110">В методе <xref:System.String.IndexOf%2A> учитывается регистр и используется текущий язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="93899-110">The <xref:System.String.IndexOf%2A> method is case-sensitive and uses the current culture.</span></span>

<span data-ttu-id="93899-111">Для оптимального управления ошибками может потребоваться заключить Поиск строки в блок `Try` блока [try... Перехватить... Построение оператора finally](../../../language-reference/statements/try-catch-finally-statement.md) .</span><span class="sxs-lookup"><span data-stu-id="93899-111">For optimal error control, you might want to enclose the string search in the `Try` block of a [Try...Catch...Finally Statement](../../../language-reference/statements/try-catch-finally-statement.md) construction.</span></span>

## <a name="see-also"></a><span data-ttu-id="93899-112">См. также</span><span class="sxs-lookup"><span data-stu-id="93899-112">See also</span></span>

- <xref:System.String.IndexOf%2A>
- [<span data-ttu-id="93899-113">Оператор Try...Catch...Finally</span><span class="sxs-lookup"><span data-stu-id="93899-113">Try...Catch...Finally Statement</span></span>](../../../language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="93899-114">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="93899-114">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
- [<span data-ttu-id="93899-115">Строки</span><span class="sxs-lookup"><span data-stu-id="93899-115">Strings</span></span>](index.md)
