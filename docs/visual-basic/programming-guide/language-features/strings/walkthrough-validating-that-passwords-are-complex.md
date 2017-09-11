---
title: "Проверка сложности паролей (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- String data type, validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8d636c1e43de6a108cdc217cb21aaf7689e175f7
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="e106f-102">Пошаговое руководство. Проверка паролей на сложность (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e106f-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="e106f-103">Этот метод проверяет некоторые характеристики строгого пароля и обновляет строковый параметр сведениями о том, какие проверки пароля завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="e106f-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="e106f-104">Пароли могут использоваться в системе безопасности для авторизации пользователя.</span><span class="sxs-lookup"><span data-stu-id="e106f-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="e106f-105">Однако пароли должны быть сложными для взлома.</span><span class="sxs-lookup"><span data-stu-id="e106f-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="e106f-106">Злоумышленники могут использовать *словарная атака* программу, которая перебирает все слова в словаре (или нескольких словарей на разных языках) и проверяет, является ли работать любое из слов в качестве пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="e106f-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="e106f-107">Можно быстро подобрать слабые пароли, такие как «Yankees» или «Mustang».</span><span class="sxs-lookup"><span data-stu-id="e106f-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="e106f-108">Более надежные пароли, такие как «? Вы «L1N3vaFiNdMeyeP@sSWerd!», гораздо реже подобрать.</span><span class="sxs-lookup"><span data-stu-id="e106f-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="e106f-109">Система защиты паролей необходимо убедиться, чтобы пользователи выбирали надежные пароли.</span><span class="sxs-lookup"><span data-stu-id="e106f-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="e106f-110">Надежный пароль является сложным (содержащим сочетание верхнего, нижнего регистра, цифры и специальные символы) и не является словом.</span><span class="sxs-lookup"><span data-stu-id="e106f-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="e106f-111">В этом примере демонстрируется проверка сложности.</span><span class="sxs-lookup"><span data-stu-id="e106f-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e106f-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e106f-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="e106f-113">Код</span><span class="sxs-lookup"><span data-stu-id="e106f-113">Code</span></span>  
 <span data-ttu-id="e106f-114">[!code-vb[VbVbcnRegEx&#1;](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e106f-114">[!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e106f-115">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e106f-115">Compiling the Code</span></span>  
 <span data-ttu-id="e106f-116">Этот метод путем передачи строки, содержащей этот пароль.</span><span class="sxs-lookup"><span data-stu-id="e106f-116">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="e106f-117">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="e106f-117">This example requires:</span></span>  
  
-   <span data-ttu-id="e106f-118">Доступ к членам <xref:System.Text.RegularExpressions>имен.</xref:System.Text.RegularExpressions></span><span class="sxs-lookup"><span data-stu-id="e106f-118">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="e106f-119">Добавление `Imports` инструкции, если в коде не используются полностью квалифицированные имена элементов.</span><span class="sxs-lookup"><span data-stu-id="e106f-119">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="e106f-120">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="e106f-120">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="e106f-121">Безопасность</span><span class="sxs-lookup"><span data-stu-id="e106f-121">Security</span></span>  
 <span data-ttu-id="e106f-122">При перемещении пароля по сети необходимо использовать безопасный метод передачи данных.</span><span class="sxs-lookup"><span data-stu-id="e106f-122">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="e106f-123">Дополнительные сведения см. в разделе [безопасности веб-приложений ASP.NET](https://msdn.microsoft.com/library/330a99hc).</span><span class="sxs-lookup"><span data-stu-id="e106f-123">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="e106f-124">Можно улучшить точность `ValidatePassword` функцию, добавив дополнительные проверки сложности:</span><span class="sxs-lookup"><span data-stu-id="e106f-124">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="e106f-125">Сравните пароль и его подстроки от имени пользователя, идентификатор пользователя и словарем определяемые приложением.</span><span class="sxs-lookup"><span data-stu-id="e106f-125">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="e106f-126">Кроме того рассматривать визуальный вид символов как эквивалент при выполнении сравнений.</span><span class="sxs-lookup"><span data-stu-id="e106f-126">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="e106f-127">Например рассматривать буквы «l» и «e» как эквиваленты цифр «1» и «3».</span><span class="sxs-lookup"><span data-stu-id="e106f-127">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="e106f-128">Если имеется только один символ верхнего регистра, убедитесь, что это не первый знак пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="e106f-128">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="e106f-129">Убедитесь, что последние два символа пароля — буквы.</span><span class="sxs-lookup"><span data-stu-id="e106f-129">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="e106f-130">Не разрешать пароли, в которых все символы введены из верхнего ряда клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="e106f-130">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e106f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e106f-131">See Also</span></span>  
 <span data-ttu-id="e106f-132"><xref:System.Text.RegularExpressions.Regex></xref:System.Text.RegularExpressions.Regex></span><span class="sxs-lookup"><span data-stu-id="e106f-132"><xref:System.Text.RegularExpressions.Regex></span></span>   
<span data-ttu-id="e106f-133"> [Безопасность веб-приложений ASP.NET](https://msdn.microsoft.com/library/330a99hc)</span><span class="sxs-lookup"><span data-stu-id="e106f-133"> [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc)</span></span>
