---
title: Практическое руководство. Проверка строк, представляющих дату или время
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5321e7a85c45ddb6ce17433bd25ce9ca2165f0a3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348404"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="a8a7b-102">Практическое руководство. Проверка строк, представляющих дату или время (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8a7b-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="a8a7b-103">В следующем примере кода задается значение `Boolean`, указывающее, представляет ли строка допустимую дату или время.</span><span class="sxs-lookup"><span data-stu-id="a8a7b-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8a7b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a8a7b-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="a8a7b-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a8a7b-105">Compile the code</span></span>  
 <span data-ttu-id="a8a7b-106">Замените `("01/01/03")` и `"9:30 PM"` на дату и время, которые необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="a8a7b-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="a8a7b-107">Строку можно заменить другой жестко заданной строкой, переменной `String` или методом, возвращающим строку, например `InputBox`.</span><span class="sxs-lookup"><span data-stu-id="a8a7b-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a8a7b-108">Надежное программирование</span><span class="sxs-lookup"><span data-stu-id="a8a7b-108">Robust Programming</span></span>  
 <span data-ttu-id="a8a7b-109">Используйте этот метод для проверки строки перед попыткой преобразования `String` в переменную `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="a8a7b-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="a8a7b-110">При проверке даты или времени сначала можно избежать создания исключения во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a8a7b-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8a7b-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="a8a7b-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="a8a7b-112">Проверка строк в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a8a7b-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
