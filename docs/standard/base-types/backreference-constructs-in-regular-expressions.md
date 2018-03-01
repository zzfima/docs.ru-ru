---
title: "Конструкции обратных ссылок в регулярных выражениях"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2ec92933bdf123412a3d489fc493d76c4a0dc0d0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="backreference-constructs-in-regular-expressions"></a><span data-ttu-id="9002a-102">Конструкции обратных ссылок в регулярных выражениях</span><span class="sxs-lookup"><span data-stu-id="9002a-102">Backreference Constructs in Regular Expressions</span></span>
<span data-ttu-id="9002a-103">Обратные ссылки предоставляют удобный способ идентификации повторяющегося символа или подстроки в строке.</span><span class="sxs-lookup"><span data-stu-id="9002a-103">Backreferences provide a convenient way to identify a repeated character or substring within a string.</span></span> <span data-ttu-id="9002a-104">Например, если входная строка содержит несколько экземпляров произвольной подстроки, можно найти первое вхождение с помощью группы записи, а затем использовать обратную ссылку для поиска последующих вхождений подстроки.</span><span class="sxs-lookup"><span data-stu-id="9002a-104">For example, if the input string contains multiple occurrences of an arbitrary substring, you can match the first occurrence with a capturing group, and then use a backreference to match subsequent occurrences of the substring.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9002a-105">Для ссылки на именованные и нумерованные захватываемые группы в строках замены используется отдельный синтаксис.</span><span class="sxs-lookup"><span data-stu-id="9002a-105">A separate syntax is used to refer to named and numbered capturing groups in replacement strings.</span></span> <span data-ttu-id="9002a-106">Для получения дополнительной информации см. [Substitutions](substitutions-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9002a-106">For more information, see [Substitutions](substitutions-in-regular-expressions.md).</span></span>  
  
 <span data-ttu-id="9002a-107">.NET определяет отдельные элементы языка для ссылки на нумерованные и именованные захватываемые группы.</span><span class="sxs-lookup"><span data-stu-id="9002a-107">.NET defines separate language elements to refer to numbered and named capturing groups.</span></span> <span data-ttu-id="9002a-108">Дополнительные сведения о группах записи см. в статье [Конструкции группирования](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="9002a-108">For more information about capturing groups, see [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).</span></span>  
  
## <a name="numbered-backreferences"></a><span data-ttu-id="9002a-109">Нумерованные обратные ссылки</span><span class="sxs-lookup"><span data-stu-id="9002a-109">Numbered Backreferences</span></span>  
 <span data-ttu-id="9002a-110">Нумерованная обратная ссылка использует следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="9002a-110">A numbered backreference uses the following syntax:</span></span>  
  
 <span data-ttu-id="9002a-111">`\` *number*</span><span class="sxs-lookup"><span data-stu-id="9002a-111">`\` *number*</span></span>  
  
 <span data-ttu-id="9002a-112">где *число* — это порядковое положение захватываемой группы в регулярном выражении.</span><span class="sxs-lookup"><span data-stu-id="9002a-112">where *number* is the ordinal position of the capturing group in the regular expression.</span></span> <span data-ttu-id="9002a-113">Например, `\4` соответствует содержимому четвертой захватываемой группы.</span><span class="sxs-lookup"><span data-stu-id="9002a-113">For example, `\4` matches the contents of the fourth capturing group.</span></span> <span data-ttu-id="9002a-114">Если параметр *число* не определен в шаблоне регулярного выражения, возникает ошибка синтаксического анализа, и обработчик регулярных выражений создает исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="9002a-114">If *number* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="9002a-115">Например, регулярное выражение `\b(\w+)\s\1` является допустимым, поскольку `(\w+)` — это первая и единственная захватываемая группа в выражении.</span><span class="sxs-lookup"><span data-stu-id="9002a-115">For example, the regular expression `\b(\w+)\s\1` is valid, because `(\w+)` is the first and only capturing group in the expression.</span></span> <span data-ttu-id="9002a-116">С другой стороны, выражение `\b(\w+)\s\2` недопустимо и создает исключение аргумента, так как захватываемая группа с номером `\2` отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9002a-116">On the other hand, `\b(\w+)\s\2` is invalid and throws an argument exception, because there is no capturing group numbered `\2`.</span></span>  
  
 <span data-ttu-id="9002a-117">Следует отметить неоднозначность такой записи, которая может означать как восьмеричные escape-коды (например, `\16`), так и `\`*число* для обратных ссылок.</span><span class="sxs-lookup"><span data-stu-id="9002a-117">Note the ambiguity between octal escape codes (such as `\16`) and `\`*number* backreferences that use the same notation.</span></span> <span data-ttu-id="9002a-118">Эта неопределенность разрешается следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9002a-118">This ambiguity is resolved as follows:</span></span>  
  
-   <span data-ttu-id="9002a-119">Выражения с `\1` по `\9` всегда интерпретируются как обратные ссылки, а не как восьмеричные коды.</span><span class="sxs-lookup"><span data-stu-id="9002a-119">The expressions `\1` through `\9` are always interpreted as backreferences, and not as octal codes.</span></span>  
  
-   <span data-ttu-id="9002a-120">Если первая цифра многоразрядного выражения — 8 или 9 (например, `\80` или `\91`), выражение интерпретируется как литерал.</span><span class="sxs-lookup"><span data-stu-id="9002a-120">If the first digit of a multidigit expression is 8 or 9 (such as `\80` or `\91`), the expression as interpreted as a literal.</span></span>  
  
-   <span data-ttu-id="9002a-121">Выражения от `\10` и более считаются обратными ссылками, если имеется обратная ссылка, соответствующая этому номеру. В противном случае они интерпретируются как восьмеричные коды.</span><span class="sxs-lookup"><span data-stu-id="9002a-121">Expressions from `\10` and greater are considered backreferences if there is a backreference corresponding to that number; otherwise, they are interpreted as octal codes.</span></span>  
  
-   <span data-ttu-id="9002a-122">Если регулярное выражение содержит обратную ссылку на неопределенный номер группы, возникает ошибка синтаксического анализа, и обработчик регулярных выражений создает исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="9002a-122">If a regular expression contains a backreference to an undefined group number, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="9002a-123">Если неоднозначность представляет проблему, можно использовать однозначное представление `\k<`*name*`>`, которое невозможно спутать с восьмеричными кодами символов.</span><span class="sxs-lookup"><span data-stu-id="9002a-123">If the ambiguity is a problem, you can use the `\k<`*name*`>` notation, which is unambiguous and cannot be confused with octal character codes.</span></span> <span data-ttu-id="9002a-124">Аналогичным образом шестнадцатеричные коды, например `\xdd`, однозначны, и их нельзя спутать с обратными ссылками.</span><span class="sxs-lookup"><span data-stu-id="9002a-124">Similarly, hexadecimal codes such as `\xdd` are unambiguous and cannot be confused with backreferences.</span></span>  
  
 <span data-ttu-id="9002a-125">В приведенном ниже примере в строке выделяются двойные словообразующие символы.</span><span class="sxs-lookup"><span data-stu-id="9002a-125">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="9002a-126">Здесь определяется регулярное выражение, `(\w)\1`, которое состоит из следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="9002a-126">It defines a regular expression, `(\w)\1`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="9002a-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="9002a-127">Element</span></span>|<span data-ttu-id="9002a-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="9002a-128">Description</span></span>|  
|-------------|-----------------|  
|`(\w)`|<span data-ttu-id="9002a-129">Совпадение со словообразующим символом и его назначение первой захватываемой группе.</span><span class="sxs-lookup"><span data-stu-id="9002a-129">Match a word character and assign it to the first capturing group.</span></span>|  
|`\1`|<span data-ttu-id="9002a-130">Совпадение со следующим символом, значение которого совпадает с первой захватываемой группой.</span><span class="sxs-lookup"><span data-stu-id="9002a-130">Match the next character that is the same as the value of the first capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
 [!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]  
  
## <a name="named-backreferences"></a><span data-ttu-id="9002a-131">Именованные обратные ссылки</span><span class="sxs-lookup"><span data-stu-id="9002a-131">Named Backreferences</span></span>  
 <span data-ttu-id="9002a-132">Именованная обратная ссылка задается с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="9002a-132">A named backreference is defined by using the following syntax:</span></span>  
  
 <span data-ttu-id="9002a-133">`\k<` *имя* `>`</span><span class="sxs-lookup"><span data-stu-id="9002a-133">`\k<` *name* `>`</span></span>  
  
 <span data-ttu-id="9002a-134">или</span><span class="sxs-lookup"><span data-stu-id="9002a-134">or:</span></span>  
  
 <span data-ttu-id="9002a-135">`\k'` *name* `'`</span><span class="sxs-lookup"><span data-stu-id="9002a-135">`\k'` *name* `'`</span></span>  
  
 <span data-ttu-id="9002a-136">где *name*— это имя захватываемой группы, определенное в шаблоне регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="9002a-136">where *name* is the name of a capturing group defined in the regular expression pattern.</span></span> <span data-ttu-id="9002a-137">Если параметр *имя* не определен в шаблоне регулярного выражения, возникает ошибка синтаксического анализа, и обработчик регулярных выражений создает исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="9002a-137">If *name* is not defined in the regular expression pattern, a parsing error occurs, and the regular expression engine throws an <xref:System.ArgumentException>.</span></span>  
  
 <span data-ttu-id="9002a-138">В приведенном ниже примере в строке выделяются двойные словообразующие символы.</span><span class="sxs-lookup"><span data-stu-id="9002a-138">The following example finds doubled word characters in a string.</span></span> <span data-ttu-id="9002a-139">Здесь определяется регулярное выражение, `(?<char>\w)\k<char>`, которое состоит из следующих элементов.</span><span class="sxs-lookup"><span data-stu-id="9002a-139">It defines a regular expression, `(?<char>\w)\k<char>`, which consists of the following elements.</span></span>  
  
|<span data-ttu-id="9002a-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="9002a-140">Element</span></span>|<span data-ttu-id="9002a-141">Описание:</span><span class="sxs-lookup"><span data-stu-id="9002a-141">Description</span></span>|  
|-------------|-----------------|  
|`(?<char>\w)`|<span data-ttu-id="9002a-142">Сопоставляется с буквенным символом и назначает его группе записи с именем `char`.</span><span class="sxs-lookup"><span data-stu-id="9002a-142">Match a word character and assign it to a capturing group named `char`.</span></span>|  
|`\k<char>`|<span data-ttu-id="9002a-143">Сопоставляется со следующим символом, значение которого совпадает со значением группы записи `char`.</span><span class="sxs-lookup"><span data-stu-id="9002a-143">Match the next character that is the same as the value of the `char` capturing group.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
 [!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]  
  
 <span data-ttu-id="9002a-144">Обратите внимание, что *name* также может быть строковым представлением числа.</span><span class="sxs-lookup"><span data-stu-id="9002a-144">Note that *name* can also be the string representation of a number.</span></span> <span data-ttu-id="9002a-145">Например, далее используется регулярное выражение `(?<2>\w)\k<2>` для поиска в строке двойных словообразующих символов.</span><span class="sxs-lookup"><span data-stu-id="9002a-145">For example, the following example uses the regular expression `(?<2>\w)\k<2>` to find doubled word characters in a string.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
 [!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]  
  
## <a name="what-backreferences-match"></a><span data-ttu-id="9002a-146">С чем сопоставляются обратные ссылки</span><span class="sxs-lookup"><span data-stu-id="9002a-146">What Backreferences Match</span></span>  
 <span data-ttu-id="9002a-147">Обратная ссылка относится к самому недавнему определению группы (самому ближнему слева определению при обработке слева направо).</span><span class="sxs-lookup"><span data-stu-id="9002a-147">A backreference refers to the most recent definition of a group (the definition most immediately to the left, when matching left to right).</span></span> <span data-ttu-id="9002a-148">Если из группы создается несколько шаблонов для поиска, обратная ссылка относится к самому последнему шаблону.</span><span class="sxs-lookup"><span data-stu-id="9002a-148">When a group makes multiple captures, a backreference refers to the most recent capture.</span></span>  
  
 <span data-ttu-id="9002a-149">В примере ниже показан шаблон регулярного выражения `(?<1>a)(?<1>\1b)*`, который переопределяет именованную группу \1.</span><span class="sxs-lookup"><span data-stu-id="9002a-149">The following example includes a regular expression pattern, `(?<1>a)(?<1>\1b)*`, which redefines the \1 named group.</span></span> <span data-ttu-id="9002a-150">В следующей таблице описывается каждый шаблон регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="9002a-150">The following table describes each pattern in the regular expression.</span></span>  
  
|<span data-ttu-id="9002a-151">Шаблон</span><span class="sxs-lookup"><span data-stu-id="9002a-151">Pattern</span></span>|<span data-ttu-id="9002a-152">Описание:</span><span class="sxs-lookup"><span data-stu-id="9002a-152">Description</span></span>|  
|-------------|-----------------|  
|`(?<1>a)`|<span data-ttu-id="9002a-153">Сопоставляется с символом "a" и назначает его значение группе записи с именем `1`.</span><span class="sxs-lookup"><span data-stu-id="9002a-153">Match the character "a" and assign the result to the capturing group named `1`.</span></span>|  
|`(?<1>\1b)*`|<span data-ttu-id="9002a-154">Сопоставляется с нулем или одним вхождением группы с именем `1` рядом с символом "b" и назначает полученное значение группе записи с именем `1`.</span><span class="sxs-lookup"><span data-stu-id="9002a-154">Match 0 or 1 occurrence of the group named `1` along with a "b", and assign the result to the capturing group named `1`.</span></span>|  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
 [!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]  
  
 <span data-ttu-id="9002a-155">При сравнении регулярного выражения с входной строкой ("aababb") обработчик регулярных выражений выполняет указанные далее операции.</span><span class="sxs-lookup"><span data-stu-id="9002a-155">In comparing the regular expression with the input string ("aababb"), the regular expression engine performs the following operations:</span></span>  
  
1.  <span data-ttu-id="9002a-156">Начинается с первого символа и успешно сопоставляет "a" с выражением `(?<1>a)`.</span><span class="sxs-lookup"><span data-stu-id="9002a-156">It starts at the beginning of the string, and successfully matches "a" with the expression `(?<1>a)`.</span></span> <span data-ttu-id="9002a-157">Теперь значение группы `1` будет равно "a".</span><span class="sxs-lookup"><span data-stu-id="9002a-157">The value of the `1` group is now "a".</span></span>  
  
2.  <span data-ttu-id="9002a-158">Перемещается ко второму символу и успешно сопоставляет строку "ab" с выражением `\1b` или "ab".</span><span class="sxs-lookup"><span data-stu-id="9002a-158">It advances to the second character, and successfully matches the string "ab" with the expression `\1b`, or "ab".</span></span> <span data-ttu-id="9002a-159">Затем результат "ab" присваивается `\1`.</span><span class="sxs-lookup"><span data-stu-id="9002a-159">It then assigns the result, "ab" to `\1`.</span></span>  
  
3.  <span data-ttu-id="9002a-160">Переходит к четвертому символу.</span><span class="sxs-lookup"><span data-stu-id="9002a-160">It advances to the fourth character.</span></span> <span data-ttu-id="9002a-161">Выражение `(?<1>\1b)` должно выдать ноль или больше совпадений, поэтому он успешно сопоставляет строку "abb" с выражением `\1b`.</span><span class="sxs-lookup"><span data-stu-id="9002a-161">The expression `(?<1>\1b)` is to be matched zero or more times, so it successfully matches the string "abb" with the expression `\1b`.</span></span> <span data-ttu-id="9002a-162">Затем результат "abb" присваивается `\1`.</span><span class="sxs-lookup"><span data-stu-id="9002a-162">It assigns the result, "abb", back to `\1`.</span></span>  
  
 <span data-ttu-id="9002a-163">В этом примере `*` является циклическим квантификатором — он вычисляется многократно до тех пор, пока обработчик регулярных выражений не сможет обнаружить соответствие заданному им шаблону.</span><span class="sxs-lookup"><span data-stu-id="9002a-163">In this example, `*` is a looping quantifier -- it is evaluated repeatedly until the regular expression engine cannot match the pattern it defines.</span></span> <span data-ttu-id="9002a-164">Квантификаторы циклов не удаляют определения групп.</span><span class="sxs-lookup"><span data-stu-id="9002a-164">Looping quantifiers do not clear group definitions.</span></span>  
  
 <span data-ttu-id="9002a-165">Если для группы не было найдено ни одной подстроки, то обратная ссылка на эту группу не определена и не работает.</span><span class="sxs-lookup"><span data-stu-id="9002a-165">If a group has not captured any substrings, a backreference to that group is undefined and never matches.</span></span> <span data-ttu-id="9002a-166">Это продемонстрировано в шаблоне регулярного выражения `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, который определяется следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9002a-166">This is illustrated by the regular expression pattern `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b`, which is defined as follows:</span></span>  
  
|<span data-ttu-id="9002a-167">Шаблон</span><span class="sxs-lookup"><span data-stu-id="9002a-167">Pattern</span></span>|<span data-ttu-id="9002a-168">Описание:</span><span class="sxs-lookup"><span data-stu-id="9002a-168">Description</span></span>|  
|-------------|-----------------|  
|`\b`|<span data-ttu-id="9002a-169">Сопоставление начинается на границе слова.</span><span class="sxs-lookup"><span data-stu-id="9002a-169">Begin the match on a word boundary.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="9002a-170">Совпадение с двумя прописными буквами.</span><span class="sxs-lookup"><span data-stu-id="9002a-170">Match two uppercase letters.</span></span> <span data-ttu-id="9002a-171">Это первая группа записи.</span><span class="sxs-lookup"><span data-stu-id="9002a-171">This is the first capturing group.</span></span>|  
|`(\d{2})?`|<span data-ttu-id="9002a-172">Совпадение с нулевым или единичным вхождением двух десятичных цифр.</span><span class="sxs-lookup"><span data-stu-id="9002a-172">Match zero or one occurrence of two decimal digits.</span></span> <span data-ttu-id="9002a-173">Это вторая группа записи.</span><span class="sxs-lookup"><span data-stu-id="9002a-173">This is the second capturing group.</span></span>|  
|`(\p{Lu}{2})`|<span data-ttu-id="9002a-174">Совпадение с двумя прописными буквами.</span><span class="sxs-lookup"><span data-stu-id="9002a-174">Match two uppercase letters.</span></span> <span data-ttu-id="9002a-175">Это третья группа записи.</span><span class="sxs-lookup"><span data-stu-id="9002a-175">This is the third capturing group.</span></span>|  
|`\b`|<span data-ttu-id="9002a-176">Сопоставление заканчивается на границе слова.</span><span class="sxs-lookup"><span data-stu-id="9002a-176">End the match on a word boundary.</span></span>|  
  
 <span data-ttu-id="9002a-177">Входная строка может соответствовать этому регулярному выражению, даже если отсутствуют две десятичные цифры, которые заданы второй захватываемой группой.</span><span class="sxs-lookup"><span data-stu-id="9002a-177">An input string can match this regular expression even if the two decimal digits that are defined by the second capturing group are not present.</span></span> <span data-ttu-id="9002a-178">В следующем примере показано, что даже несмотря на то, что сопоставление является успешным, между двумя группами успешной записи найдена пустая группа.</span><span class="sxs-lookup"><span data-stu-id="9002a-178">The following example shows that even though the match is successful, an empty capturing group is found between two successful capturing groups.</span></span>  
  
 [!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
 [!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="9002a-179">См. также</span><span class="sxs-lookup"><span data-stu-id="9002a-179">See Also</span></span>  
 [<span data-ttu-id="9002a-180">Элементы языка регулярных выражений — краткий справочник</span><span class="sxs-lookup"><span data-stu-id="9002a-180">Regular Expression Language - Quick Reference</span></span>](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
