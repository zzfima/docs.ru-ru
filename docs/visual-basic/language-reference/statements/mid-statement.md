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
ms.openlocfilehash: a653e63ded04616b6b0c6bdfb26a0a673d9299fc
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576657"
---
# <a name="mid-statement"></a><span data-ttu-id="48578-102">Оператор Mid</span><span class="sxs-lookup"><span data-stu-id="48578-102">Mid Statement</span></span>
<span data-ttu-id="48578-103">Заменяет указанное число символов в `String` переменной с символами из другой строки.</span><span class="sxs-lookup"><span data-stu-id="48578-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48578-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48578-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="48578-105">Части</span><span class="sxs-lookup"><span data-stu-id="48578-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="48578-106">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="48578-106">Required.</span></span> <span data-ttu-id="48578-107">Имя `String` переменная, подлежащая изменению.</span><span class="sxs-lookup"><span data-stu-id="48578-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="48578-108">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="48578-108">Required.</span></span> <span data-ttu-id="48578-109">`Integer` выражение.</span><span class="sxs-lookup"><span data-stu-id="48578-109">`Integer` expression.</span></span> <span data-ttu-id="48578-110">Позиция знака в `Target` которой начинается замена текста.</span><span class="sxs-lookup"><span data-stu-id="48578-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="48578-111">`Start` использует однобазовый индекс.</span><span class="sxs-lookup"><span data-stu-id="48578-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="48578-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="48578-112">Optional.</span></span> <span data-ttu-id="48578-113">`Integer` выражение.</span><span class="sxs-lookup"><span data-stu-id="48578-113">`Integer` expression.</span></span> <span data-ttu-id="48578-114">Число символов для замены.</span><span class="sxs-lookup"><span data-stu-id="48578-114">Number of characters to replace.</span></span> <span data-ttu-id="48578-115">Если не указано, все `String` используется.</span><span class="sxs-lookup"><span data-stu-id="48578-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="48578-116">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="48578-116">Required.</span></span> <span data-ttu-id="48578-117">`String` выражение, которое заменяет часть `Target`.</span><span class="sxs-lookup"><span data-stu-id="48578-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="48578-118">Исключения</span><span class="sxs-lookup"><span data-stu-id="48578-118">Exceptions</span></span>  
  
|<span data-ttu-id="48578-119">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="48578-119">Exception type</span></span>|<span data-ttu-id="48578-120">Условие</span><span class="sxs-lookup"><span data-stu-id="48578-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="48578-121">`Start` < = 0 или `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="48578-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48578-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="48578-122">Remarks</span></span>  
 <span data-ttu-id="48578-123">Число заменяемых знаков всегда будет меньше или равно числу символов в `Target`.</span><span class="sxs-lookup"><span data-stu-id="48578-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="48578-124">Visual Basic имеет <xref:Microsoft.VisualBasic.Strings.Mid%2A> функции и `Mid` инструкции.</span><span class="sxs-lookup"><span data-stu-id="48578-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="48578-125">Эти элементы, которые работают на указанное число знаков в строке, но `Mid` функция возвращает символов при `Mid` инструкция заменяет символы.</span><span class="sxs-lookup"><span data-stu-id="48578-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="48578-126">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="48578-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48578-127">`MidB` Инструкция из более ранних версиях Visual Basic заменяет подстроки в байтах, а не символы.</span><span class="sxs-lookup"><span data-stu-id="48578-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="48578-128">Он используется главным образом для преобразования строк в приложениях двухбайтовой кодировки (DBCS).</span><span class="sxs-lookup"><span data-stu-id="48578-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="48578-129">Все строки Visual Basic, в формате Юникод, и `MidB` больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="48578-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48578-130">Пример</span><span class="sxs-lookup"><span data-stu-id="48578-130">Example</span></span>  
 <span data-ttu-id="48578-131">В этом примере используется `Mid` инструкцию, чтобы заменить указанное число символов в строковой переменной символами из другой строки.</span><span class="sxs-lookup"><span data-stu-id="48578-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="48578-132">Требования</span><span class="sxs-lookup"><span data-stu-id="48578-132">Requirements</span></span>  
 <span data-ttu-id="48578-133">**Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="48578-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="48578-134">**Модуль:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="48578-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="48578-135">**Сборка:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48578-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48578-136">См. также</span><span class="sxs-lookup"><span data-stu-id="48578-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="48578-137">Строки</span><span class="sxs-lookup"><span data-stu-id="48578-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="48578-138">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="48578-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
