---
title: Оператор Mid (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: ea22af2eb896542bfc329e087101608e08c45107
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581474"
---
# <a name="mid-statement"></a><span data-ttu-id="0f2ac-102">Оператор Mid</span><span class="sxs-lookup"><span data-stu-id="0f2ac-102">Mid Statement</span></span>
<span data-ttu-id="0f2ac-103">Заменяет указанное число символов в переменной `String` символами из другой строки.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f2ac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f2ac-104">Syntax</span></span>  
  
```vb  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="0f2ac-105">Части</span><span class="sxs-lookup"><span data-stu-id="0f2ac-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="0f2ac-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-106">Required.</span></span> <span data-ttu-id="0f2ac-107">Имя изменяемой переменной `String`.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="0f2ac-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-108">Required.</span></span> <span data-ttu-id="0f2ac-109">выражение `Integer`.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-109">`Integer` expression.</span></span> <span data-ttu-id="0f2ac-110">Позицию символа в `Target`, где начинается замена текста.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="0f2ac-111">`Start` использует индекс, отсчитываемый от единицы.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="0f2ac-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-112">Optional.</span></span> <span data-ttu-id="0f2ac-113">выражение `Integer`.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-113">`Integer` expression.</span></span> <span data-ttu-id="0f2ac-114">Число символов для замены.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-114">Number of characters to replace.</span></span> <span data-ttu-id="0f2ac-115">Если этот параметр опущен, используется все `String`.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="0f2ac-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-116">Required.</span></span> <span data-ttu-id="0f2ac-117">`String` выражение, которое заменяет часть `Target`.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="0f2ac-118">Исключения</span><span class="sxs-lookup"><span data-stu-id="0f2ac-118">Exceptions</span></span>  
  
|<span data-ttu-id="0f2ac-119">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="0f2ac-119">Exception type</span></span>|<span data-ttu-id="0f2ac-120">Условие</span><span class="sxs-lookup"><span data-stu-id="0f2ac-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="0f2ac-121">`Start` < = 0 или `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f2ac-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="0f2ac-122">Remarks</span></span>  
 <span data-ttu-id="0f2ac-123">Число заменяемых символов всегда меньше или равно числу символов в `Target`.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="0f2ac-124">Visual Basic содержит функцию <xref:Microsoft.VisualBasic.Strings.Mid%2A> и инструкцию `Mid`.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="0f2ac-125">Эти элементы работают с указанным числом символов в строке, но функция `Mid` возвращает символы, пока оператор `Mid` заменяет символы.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="0f2ac-126">Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f2ac-127">@No__t_0ная инструкция более ранних версий Visual Basic заменяет подстроку в байтах, а не на символы.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="0f2ac-128">Он используется в основном для преобразования строк в приложениях с двухбайтовой кодировкой (DBCS).</span><span class="sxs-lookup"><span data-stu-id="0f2ac-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="0f2ac-129">Все строки Visual Basic в Юникоде, а `MidB` больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f2ac-130">Пример</span><span class="sxs-lookup"><span data-stu-id="0f2ac-130">Example</span></span>  
 <span data-ttu-id="0f2ac-131">В этом примере используется оператор `Mid` для замены указанного числа символов в строковой переменной символами из другой строки.</span><span class="sxs-lookup"><span data-stu-id="0f2ac-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="0f2ac-132">Требования</span><span class="sxs-lookup"><span data-stu-id="0f2ac-132">Requirements</span></span>  
 <span data-ttu-id="0f2ac-133">**Пространство имен:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="0f2ac-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="0f2ac-134">**Модуль:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="0f2ac-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="0f2ac-135">**Сборка:** Библиотека времени выполнения Visual Basic (в Microsoft. VisualBasic. dll)</span><span class="sxs-lookup"><span data-stu-id="0f2ac-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2ac-136">См. также</span><span class="sxs-lookup"><span data-stu-id="0f2ac-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="0f2ac-137">Строки</span><span class="sxs-lookup"><span data-stu-id="0f2ac-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="0f2ac-138">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0f2ac-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
