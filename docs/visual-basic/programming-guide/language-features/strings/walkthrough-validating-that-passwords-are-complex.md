---
title: Проверка сложности паролей (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: ff0ac933be917b5604966240ff1fbd331a34ba77
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663629"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="85d12-102">Пошаговое руководство. Проверка паролей на сложность (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85d12-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="85d12-103">Этот метод проверяет некоторые характеристики надежный пароль и обновляет строковый параметр с информацией о том, какие проверки пароля завершается ошибкой.</span><span class="sxs-lookup"><span data-stu-id="85d12-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="85d12-104">Пароли могут использоваться в системе безопасности для авторизации пользователя.</span><span class="sxs-lookup"><span data-stu-id="85d12-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="85d12-105">Тем не менее должны быть сложными для взлома паролей.</span><span class="sxs-lookup"><span data-stu-id="85d12-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="85d12-106">Злоумышленники могут использовать *атака перебором по словарю* программы, которая перебирает все слова в словаре (или несколько словарей на разных языках) и проверяет, является ли любое из слов работать в качестве пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="85d12-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="85d12-107">Слабые пароли, такие как «Yankees» или «Самой» можно быстро подобрать.</span><span class="sxs-lookup"><span data-stu-id="85d12-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="85d12-108">Более надежные пароли, такие как «? Вы "L1N3vaFiNdMeyeP@sSWerd!», гораздо реже подвергаться.</span><span class="sxs-lookup"><span data-stu-id="85d12-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="85d12-109">Системы, защищенной паролем следует убедиться, что пользователи выбирать надежные пароли.</span><span class="sxs-lookup"><span data-stu-id="85d12-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="85d12-110">Надежный пароль является сложным (содержащее сочетание символов верхнего регистра, нижнего регистра, цифры и специальные) и не слова.</span><span class="sxs-lookup"><span data-stu-id="85d12-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="85d12-111">В этом примере демонстрируется проверка сложности.</span><span class="sxs-lookup"><span data-stu-id="85d12-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85d12-112">Пример</span><span class="sxs-lookup"><span data-stu-id="85d12-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="85d12-113">Код</span><span class="sxs-lookup"><span data-stu-id="85d12-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="85d12-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="85d12-114">Compiling the Code</span></span>  
 <span data-ttu-id="85d12-115">Этот метод путем передачи строки, содержащей этот пароль.</span><span class="sxs-lookup"><span data-stu-id="85d12-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="85d12-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="85d12-116">This example requires:</span></span>  
  
- <span data-ttu-id="85d12-117">Доступ к членам пространства имен <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="85d12-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="85d12-118">Добавьте оператор `Imports`, если в коде не используются полные имена членов.</span><span class="sxs-lookup"><span data-stu-id="85d12-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="85d12-119">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="85d12-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="85d12-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="85d12-120">Security</span></span>  
 <span data-ttu-id="85d12-121">Если вы перемещаете пароля по сети, необходимо использовать безопасный метод передачи данных.</span><span class="sxs-lookup"><span data-stu-id="85d12-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="85d12-122">Дополнительные сведения см. в разделе [безопасности веб-приложений ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="85d12-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="85d12-123">Можно повысить точность `ValidatePassword` функцию, добавив дополнительные проверки сложности:</span><span class="sxs-lookup"><span data-stu-id="85d12-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="85d12-124">Сравните пароль и его подстроки от имени пользователя, идентификатор пользователя и словарю определяемые приложением.</span><span class="sxs-lookup"><span data-stu-id="85d12-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="85d12-125">Кроме того рассматривать визуальный вид символов как эквивалентные, при выполнении сравнений.</span><span class="sxs-lookup"><span data-stu-id="85d12-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="85d12-126">Например считайте буквы «l» и «e» эквиваленты цифр «1» и «3».</span><span class="sxs-lookup"><span data-stu-id="85d12-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="85d12-127">Если имеется только один символ верхнего регистра, убедитесь, что это не первый знак пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="85d12-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="85d12-128">Убедитесь, что последние два символа пароля — буквы.</span><span class="sxs-lookup"><span data-stu-id="85d12-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="85d12-129">Запретить паролей, в которых все символы вводятся в верхней строке на клавиатуре.</span><span class="sxs-lookup"><span data-stu-id="85d12-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85d12-130">См. также</span><span class="sxs-lookup"><span data-stu-id="85d12-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="85d12-131">[Безопасность веб-приложений ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="85d12-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
