---
title: Сложность проверки паролей
ms.date: 07/20/2015
helpviewer_keywords:
- String data type [Visual Basic], validation
ms.assetid: 5d9a918f-6c1f-41a3-a019-b5c2b8ce0381
ms.openlocfilehash: 6e8697379a6fbb5cc15b60291e5b822897c2c013
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348327"
---
# <a name="walkthrough-validating-that-passwords-are-complex-visual-basic"></a><span data-ttu-id="83e77-102">Пошаговое руководство. Проверка паролей на сложность (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83e77-102">Walkthrough: Validating That Passwords Are Complex (Visual Basic)</span></span>
<span data-ttu-id="83e77-103">Этот метод проверяет некоторые характеристики строгого пароля и обновляет строковый параметр, используя сведения о том, какие проверки пароля завершился ошибкой.</span><span class="sxs-lookup"><span data-stu-id="83e77-103">This method checks for some strong-password characteristics and updates a string parameter with information about which checks the password fails.</span></span>  
  
 <span data-ttu-id="83e77-104">Пароли можно использовать в защищенной системе для авторизации пользователя.</span><span class="sxs-lookup"><span data-stu-id="83e77-104">Passwords can be used in a secure system to authorize a user.</span></span> <span data-ttu-id="83e77-105">Тем не менее пароли должны быть сложными для взлома неавторизованными пользователями.</span><span class="sxs-lookup"><span data-stu-id="83e77-105">However, the passwords must be difficult for unauthorized users to guess.</span></span> <span data-ttu-id="83e77-106">Злоумышленники могут использовать *словарную* программу для атаки, которая перебирает все слова в словаре (или несколько словарей на разных языках) и проверяет, работает ли какое-либо из слов в качестве пароля пользователя.</span><span class="sxs-lookup"><span data-stu-id="83e77-106">Attackers can use a *dictionary attack* program, which iterates through all of the words in a dictionary (or multiple dictionaries in different languages) and tests whether any of the words work as a user's password.</span></span> <span data-ttu-id="83e77-107">Ненадежные пароли, например "Янкиз" или "Мустанг", можно быстро угадать.</span><span class="sxs-lookup"><span data-stu-id="83e77-107">Weak passwords such as "Yankees" or "Mustang" can be guessed quickly.</span></span> <span data-ttu-id="83e77-108">Более надежные пароли, например "? "L1N3vaFiNdMeyeP@sSWerd!", скорее всего, будут догадаться.</span><span class="sxs-lookup"><span data-stu-id="83e77-108">Stronger passwords, such as "?You'L1N3vaFiNdMeyeP@sSWerd!", are much less likely to be guessed.</span></span> <span data-ttu-id="83e77-109">Система, защищенная паролем, должна гарантировать, что пользователи будут выбирать надежные пароли.</span><span class="sxs-lookup"><span data-stu-id="83e77-109">A password-protected system should ensure that users choose strong passwords.</span></span>  
  
 <span data-ttu-id="83e77-110">Надежный пароль является сложным (он содержит сочетание прописных и строчных букв, цифр и специальных символов) и не является словом.</span><span class="sxs-lookup"><span data-stu-id="83e77-110">A strong password is complex (containing a mixture of uppercase, lowercase, numeric, and special characters) and is not a word.</span></span> <span data-ttu-id="83e77-111">В этом примере показано, как проверить сложность.</span><span class="sxs-lookup"><span data-stu-id="83e77-111">This example demonstrates how to verify complexity.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83e77-112">Пример</span><span class="sxs-lookup"><span data-stu-id="83e77-112">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="83e77-113">Код</span><span class="sxs-lookup"><span data-stu-id="83e77-113">Code</span></span>  
 [!code-vb[VbVbcnRegEx#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83e77-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="83e77-114">Compiling the Code</span></span>  
 <span data-ttu-id="83e77-115">Вызовите этот метод, передав строку, содержащую этот пароль.</span><span class="sxs-lookup"><span data-stu-id="83e77-115">Call this method by passing the string that contains that password.</span></span>  
  
 <span data-ttu-id="83e77-116">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="83e77-116">This example requires:</span></span>  
  
- <span data-ttu-id="83e77-117">Доступ к членам пространства имен <xref:System.Text.RegularExpressions>.</span><span class="sxs-lookup"><span data-stu-id="83e77-117">Access to the members of the <xref:System.Text.RegularExpressions> namespace.</span></span> <span data-ttu-id="83e77-118">Добавьте оператор `Imports`, если в коде не используются полные имена членов.</span><span class="sxs-lookup"><span data-stu-id="83e77-118">Add an `Imports` statement if you are not fully qualifying member names in your code.</span></span> <span data-ttu-id="83e77-119">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="83e77-119">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
## <a name="security"></a><span data-ttu-id="83e77-120">Безопасность</span><span class="sxs-lookup"><span data-stu-id="83e77-120">Security</span></span>  
 <span data-ttu-id="83e77-121">При перемещении пароля по сети необходимо использовать безопасный метод передачи данных.</span><span class="sxs-lookup"><span data-stu-id="83e77-121">If you're moving the password across a network, you need to use a secure method for transferring data.</span></span> <span data-ttu-id="83e77-122">Дополнительные сведения см. в разделе [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="83e77-122">For more information, see [ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100)).</span></span>
  
 <span data-ttu-id="83e77-123">Точность функции `ValidatePassword` можно повысить, добавив дополнительные проверки сложности:</span><span class="sxs-lookup"><span data-stu-id="83e77-123">You can improve the accuracy of the `ValidatePassword` function by adding additional complexity checks:</span></span>  
  
- <span data-ttu-id="83e77-124">Сравните пароль и его подстроки с именем пользователя, идентификатором пользователя и словарем, определяемым приложением.</span><span class="sxs-lookup"><span data-stu-id="83e77-124">Compare the password and its substrings against the user's name, user identifier, and an application-defined dictionary.</span></span> <span data-ttu-id="83e77-125">Кроме того, при выполнении сравнений следует рассматривать визуально схожие символы как эквивалентные.</span><span class="sxs-lookup"><span data-stu-id="83e77-125">In addition, treat visually similar characters as equivalent when performing the comparisons.</span></span> <span data-ttu-id="83e77-126">Например, буквы "l" и "e" считаются эквивалентными цифрам "1" и "3".</span><span class="sxs-lookup"><span data-stu-id="83e77-126">For example, treat the letters "l" and "e" as equivalent to the numerals "1" and "3".</span></span>  
  
- <span data-ttu-id="83e77-127">Если имеется только один символ в верхнем регистре, убедитесь, что он не является первым символом пароля.</span><span class="sxs-lookup"><span data-stu-id="83e77-127">If there is only one uppercase character, make sure it is not the password's first character.</span></span>  
  
- <span data-ttu-id="83e77-128">Убедитесь, что последние два символа пароля являются буквенными символами.</span><span class="sxs-lookup"><span data-stu-id="83e77-128">Make sure that the last two characters of the password are letter characters.</span></span>  
  
- <span data-ttu-id="83e77-129">Не разрешайте пароли, в которых все символы введены из верхней строки клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="83e77-129">Do not allow passwords in which all the symbols are entered from the keyboard's top row.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e77-130">См. также</span><span class="sxs-lookup"><span data-stu-id="83e77-130">See also</span></span>

- <xref:System.Text.RegularExpressions.Regex>
- <span data-ttu-id="83e77-131">[Безопасность веб-приложений ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="83e77-131">[ASP.NET Web Application Security](https://docs.microsoft.com/previous-versions/aspnet/330a99hc(v=vs.100))</span></span>
