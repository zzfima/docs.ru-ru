---
title: "Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed3201ef2bbef97eebbafa5ef128ca015adac013
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="11de9-102">Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11de9-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="11de9-103">В следующем примере кода `Boolean` значение, указывающее, представляет ли строка допустимую дату или время.</span><span class="sxs-lookup"><span data-stu-id="11de9-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11de9-104">Пример</span><span class="sxs-lookup"><span data-stu-id="11de9-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11de9-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="11de9-105">Compiling the Code</span></span>  
 <span data-ttu-id="11de9-106">Замените `("01/01/03")` и `"9:30 PM"` с указанием даты и времени, который требуется проверить.</span><span class="sxs-lookup"><span data-stu-id="11de9-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="11de9-107">Можно заменить строки с другой строкой жестко `String` переменной, или с помощью метода, возвращающего строку, например `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="11de9-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="11de9-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="11de9-108">Robust Programming</span></span>  
 <span data-ttu-id="11de9-109">Используйте этот метод для проверки строки перед попыткой преобразования `String` для `DateTime` переменной.</span><span class="sxs-lookup"><span data-stu-id="11de9-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="11de9-110">Проверив дату или время сначала, можно избежать возникновения исключений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="11de9-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11de9-111">См. также</span><span class="sxs-lookup"><span data-stu-id="11de9-111">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [<span data-ttu-id="11de9-112">Проверка строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11de9-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
