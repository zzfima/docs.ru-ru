---
title: "Оператор Mid | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
dev_langs:
- VB
helpviewer_keywords:
- substrings, Mid statement
- strings [Visual Basic], substrings
- Mid statement
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e94500c8bd7f2c6351c91ba028c1ad6d8d3dd4c3
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="mid-statement"></a><span data-ttu-id="27d60-102">Оператор Mid</span><span class="sxs-lookup"><span data-stu-id="27d60-102">Mid Statement</span></span>
<span data-ttu-id="27d60-103">Заменяет указанное число знаков в `String` переменной на знаки из другой строки.</span><span class="sxs-lookup"><span data-stu-id="27d60-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27d60-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27d60-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="27d60-105">Части</span><span class="sxs-lookup"><span data-stu-id="27d60-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="27d60-106">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="27d60-106">Required.</span></span> <span data-ttu-id="27d60-107">Имя `String` переменной для изменения.</span><span class="sxs-lookup"><span data-stu-id="27d60-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="27d60-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="27d60-108">Required.</span></span> <span data-ttu-id="27d60-109">`Integer`выражение.</span><span class="sxs-lookup"><span data-stu-id="27d60-109">`Integer` expression.</span></span> <span data-ttu-id="27d60-110">Позиция знака в `Target` начинается замена текста.</span><span class="sxs-lookup"><span data-stu-id="27d60-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="27d60-111">`Start`использует индекс от единицы.</span><span class="sxs-lookup"><span data-stu-id="27d60-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="27d60-112">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="27d60-112">Optional.</span></span> <span data-ttu-id="27d60-113">`Integer`выражение.</span><span class="sxs-lookup"><span data-stu-id="27d60-113">`Integer` expression.</span></span> <span data-ttu-id="27d60-114">Число знаков для замены.</span><span class="sxs-lookup"><span data-stu-id="27d60-114">Number of characters to replace.</span></span> <span data-ttu-id="27d60-115">Если не указано, все `String` используется.</span><span class="sxs-lookup"><span data-stu-id="27d60-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="27d60-116">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="27d60-116">Required.</span></span> <span data-ttu-id="27d60-117">`String`выражение, которое заменяет часть `Target`.</span><span class="sxs-lookup"><span data-stu-id="27d60-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="27d60-118">Исключения</span><span class="sxs-lookup"><span data-stu-id="27d60-118">Exceptions</span></span>  
  
|<span data-ttu-id="27d60-119">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="27d60-119">Exception type</span></span>|<span data-ttu-id="27d60-120">Условие</span><span class="sxs-lookup"><span data-stu-id="27d60-120">Condition</span></span>|  
|--------------------|---------------|  
|<span data-ttu-id="27d60-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="27d60-121"><xref:System.ArgumentException></span></span>|<span data-ttu-id="27d60-122">`Start`<= 0="" or=""></=>`Length`< 0.></ 0.></span><span class="sxs-lookup"><span data-stu-id="27d60-122">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27d60-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="27d60-123">Remarks</span></span>  
 <span data-ttu-id="27d60-124">Число заменяемых знаков всегда будет меньше или равно числу символов в `Target`.</span><span class="sxs-lookup"><span data-stu-id="27d60-124">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="27d60-125">Visual Basic имеет <xref:Microsoft.VisualBasic.Strings.Mid%2A>функции и `Mid` инструкции.</xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="27d60-125">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="27d60-126">Эти элементы, как работают на указанное число знаков в строке, но `Mid` функция возвращает символы при `Mid` инструкция заменяет символы.</span><span class="sxs-lookup"><span data-stu-id="27d60-126">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="27d60-127">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="27d60-127">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27d60-128">`MidB` Инструкции более ранних версиях Visual Basic заменяет подстроку в байтах, а не символы.</span><span class="sxs-lookup"><span data-stu-id="27d60-128">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="27d60-129">Он используется главным образом для преобразования строк в приложениях с двухбайтовой кодировки (DBCS).</span><span class="sxs-lookup"><span data-stu-id="27d60-129">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="27d60-130">Все строки Visual Basic кодируются в Юникоде, и `MidB` больше не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="27d60-130">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d60-131">Пример</span><span class="sxs-lookup"><span data-stu-id="27d60-131">Example</span></span>  
 <span data-ttu-id="27d60-132">В этом примере используется `Mid` инструкции для замены указанное число символов в строковой переменной на знаки из другой строки.</span><span class="sxs-lookup"><span data-stu-id="27d60-132">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 <span data-ttu-id="27d60-133">[!code-vb[VbVbalrStrings&#5;](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="27d60-133">[!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27d60-134">Требования</span><span class="sxs-lookup"><span data-stu-id="27d60-134">Requirements</span></span>  
 <span data-ttu-id="27d60-135">**Пространство имен:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="27d60-135">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="27d60-136">**Модуль:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="27d60-136">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="27d60-137">**Сборка:**[!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]</span><span class="sxs-lookup"><span data-stu-id="27d60-137">**Assembly:** [!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d60-138">См. также</span><span class="sxs-lookup"><span data-stu-id="27d60-138">See Also</span></span>  
 <span data-ttu-id="27d60-139"><xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="27d60-139"><xref:Microsoft.VisualBasic.Strings.Mid%2A></span></span>   
<span data-ttu-id="27d60-140"> [Строки](../../../visual-basic/programming-guide/language-features/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="27d60-140"> [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md) </span></span>  
<span data-ttu-id="27d60-141"> [Знакомство со строками в Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span><span class="sxs-lookup"><span data-stu-id="27d60-141"> [Introduction to Strings in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span></span>
