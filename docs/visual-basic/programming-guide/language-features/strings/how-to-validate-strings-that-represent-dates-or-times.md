---
title: Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: f24ff05e48327c21c02eb92b07db17266f743a80
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58815234"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="e1288-102">Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1288-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="e1288-103">В следующем примере кода `Boolean` значение, указывающее, представляет ли строка допустимой датой или временем.</span><span class="sxs-lookup"><span data-stu-id="e1288-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1288-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e1288-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1288-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e1288-105">Compiling the Code</span></span>  
 <span data-ttu-id="e1288-106">Замените `("01/01/03")` и `"9:30 PM"` с датой и временем, нужно проверить.</span><span class="sxs-lookup"><span data-stu-id="e1288-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="e1288-107">Можно заменить строку другой строкой, жестко `String` переменной, или с методом, возвращает строку, например `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="e1288-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="e1288-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="e1288-108">Robust Programming</span></span>  
 <span data-ttu-id="e1288-109">Используйте этот метод для проверки строки перед попыткой преобразования `String` для `DateTime` переменной.</span><span class="sxs-lookup"><span data-stu-id="e1288-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="e1288-110">Сначала проверить дату или время, позволяет избежать возникновения исключений во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1288-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1288-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e1288-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="e1288-112">Проверка строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e1288-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
