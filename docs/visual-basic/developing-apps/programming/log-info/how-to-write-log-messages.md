---
title: Как выполнить Запись сообщений в журнал (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: c12d0cde7d8128400769cd2e93361bb10e08f59b
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967026"
---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="baf48-102">Как выполнить Запись сообщений в журнал (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="baf48-102">How to: Write Log Messages (Visual Basic)</span></span>
<span data-ttu-id="baf48-103">Для записи в журнал информации о приложении можно использовать объекты `My.Application.Log` и `My.Log` .</span><span class="sxs-lookup"><span data-stu-id="baf48-103">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="baf48-104">В этом примере показано использование метода `My.Application.Log.WriteEntry` для записи в журнал данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="baf48-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>  
  
 <span data-ttu-id="baf48-105">Для записи в журнал информации об исключениях используйте метод `My.Application.Log.WriteException`; см. раздел [Практическое руководство. Исключения журналов](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="baf48-105">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="baf48-106">Пример</span><span class="sxs-lookup"><span data-stu-id="baf48-106">Example</span></span>  
 <span data-ttu-id="baf48-107">В этом примере используется метод `My.Application.Log.WriteEntry` для записи данных трассировки.</span><span class="sxs-lookup"><span data-stu-id="baf48-107">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>  
  
 [!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="baf48-108">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="baf48-108">.NET Framework Security</span></span>  
 <span data-ttu-id="baf48-109">Убедитесь в том, что записываемые в журнал данные не включают конфиденциальных сведений, например паролей пользователей.</span><span class="sxs-lookup"><span data-stu-id="baf48-109">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="baf48-110">Дополнительные сведения см. в разделе [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="baf48-110">For more information, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf48-111">См. также</span><span class="sxs-lookup"><span data-stu-id="baf48-111">See also</span></span>
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="baf48-112">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="baf48-112">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="baf48-113">Практическое руководство. Исплючения журналов</span><span class="sxs-lookup"><span data-stu-id="baf48-113">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="baf48-114">Пошаговое руководство: Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="baf48-114">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="baf48-115">Пошаговое руководство: Изменение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="baf48-115">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="baf48-116">Пошаговое руководство: Фильтрация вывода My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="baf48-116">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)
