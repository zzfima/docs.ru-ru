---
title: "Проверка сложности паролей (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bdbe5f385c6b7a0898c4907b0d8afabdaed06fa0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="adcb4-102">Пошаговое руководство. Проверка паролей на сложность (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="adcb4-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="adcb4-103">Этот метод проверяет некоторые характеристики надежного пароля и обновляет строковый параметр с информацией о том, какие проверки пароля завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="adcb4-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="adcb4-104">Пароли могут использоваться в системе безопасности для авторизации пользователя.</span><span class="sxs-lookup"><span data-stu-id="adcb4-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="adcb4-105">Однако пароли должны быть трудно несанкционированным пользователям угадать.</span><span class="sxs-lookup"><span data-stu-id="adcb4-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="adcb4-106">Злоумышленники могут использовать *атака перебором по словарю* программу, которая перебирает все слова в словаре (или нескольких словарей на разных языках) и проверяет, является ли любое из слов может использоваться в качестве пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="adcb4-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="adcb4-107">Можно быстро подобрать слабые пароли, такие как «"Командой Янки"» или «Mustang».</span><span class="sxs-lookup"><span data-stu-id="adcb4-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="adcb4-108">Более надежные пароли, такие как «? Вы "L1N3vaFiNdMeyeP@sSWerd!», скорее всего намного менее подобрать.</span><span class="sxs-lookup"><span data-stu-id="adcb4-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="adcb4-109">Системы, защищенные паролем следует убедиться, что пользователи выбирать надежные пароли.</span><span class="sxs-lookup"><span data-stu-id="adcb4-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="adcb4-110">Надежный пароль является сложным (содержащим сочетание верхнем регистре, нижнем регистре, цифры и специальные символы) и не является словом.</span><span class="sxs-lookup"><span data-stu-id="adcb4-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="adcb4-111">В этом примере демонстрируется проверка сложности.</span><span class="sxs-lookup"><span data-stu-id="adcb4-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adcb4-112">Пример</span><span class="sxs-lookup"><span data-stu-id="adcb4-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="adcb4-113">Код</span><span class="sxs-lookup"><span data-stu-id="adcb4-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/walkthrough-validating-that-passwords-are-complex_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="adcb4-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="adcb4-114">Compiling the Code</span></span>  
 <span data-ttu-id="adcb4-115">Этот метод путем передачи строки, содержащей этот пароль.</span><span class="sxs-lookup"><span data-stu-id="adcb4-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="adcb4-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="adcb4-116">This example requires:</span></span>  
  
-   <span data-ttu-id="adcb4-117">Доступ к членам пространства имен <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="adcb4-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="adcb4-118">Добавьте оператор `Imports`, если в коде не используются полные имена членов.</span><span class="sxs-lookup"><span data-stu-id="adcb4-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="adcb4-119">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="adcb4-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="adcb4-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="adcb4-120">Security</span></span>  
 <span data-ttu-id="adcb4-121">При перемещении пароля по сети необходимо использовать безопасный метод передачи данных.</span><span class="sxs-lookup"><span data-stu-id="adcb4-121">If you are moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="adcb4-122">Дополнительные сведения см. в разделе [безопасности веб-приложений ASP.NET](https://msdn.microsoft.com/library/330a99hc).</span><span class="sxs-lookup"><span data-stu-id="adcb4-122">For more information, see [ASP.NET Web Application Security](https://msdn.microsoft.com/library/330a99hc).</span></span>  
  
 <span data-ttu-id="adcb4-123">Можно улучшить точность `ValidatePassword` функцию, добавив дополнительные проверки сложности:</span><span class="sxs-lookup"><span data-stu-id="adcb4-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
-   <span data-ttu-id="adcb4-124">Сравните пароль и его подстроки с именем пользователя, идентификатор пользователя и словарю определяемые приложением.</span><span class="sxs-lookup"><span data-stu-id="adcb4-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="adcb4-125">Кроме того рассматривать визуальный вид символов как эквивалентные, при выполнении сравнений.</span><span class="sxs-lookup"><span data-stu-id="adcb4-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="adcb4-126">Например рассматривать буквы «l» и «e» как эквиваленты цифр «1» и «3».</span><span class="sxs-lookup"><span data-stu-id="adcb4-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
-   <span data-ttu-id="adcb4-127">Если имеется только один символ верхнего регистра, убедитесь, что это не первый знак пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="adcb4-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
-   <span data-ttu-id="adcb4-128">Убедитесь, что последние два символа пароля — буквы.</span><span class="sxs-lookup"><span data-stu-id="adcb4-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
-   <span data-ttu-id="adcb4-129">Не разрешать пароли, в которых все символы вводятся с клавиатуры в верхней строке.</span><span class="sxs-lookup"><span data-stu-id="adcb4-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adcb4-130">См. также</span><span class="sxs-lookup"><span data-stu-id="adcb4-130">See Also</span></span>  
 <xref:System.Text.RegularExpressions.Regex>  
 [<span data-ttu-id="adcb4-131">Безопасность веб-приложений ASP.NET</span><span class="sxs-lookup"><span data-stu-id="adcb4-131">ASP.NET Web Application Security</span></span>](https://msdn.microsoft.com/library/330a99hc)
