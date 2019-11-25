---
title: 'Устранение неполадок: Прослушиватели журнала'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: dd139935dae7fe4d1334b861e6590df29bab7202
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346860"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="d69ef-102">Устранение неполадок: прослушиватели журнала (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d69ef-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="d69ef-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.</span><span class="sxs-lookup"><span data-stu-id="d69ef-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="d69ef-104">Чтобы определить, какие прослушиватели журналов получают эти сообщения, см. раздел [Пошаговое руководство. Определение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="d69ef-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="d69ef-105">Объект `Log` может использовать фильтрацию журнала для ограничения объема данных, регистрируемых в журнале.</span><span class="sxs-lookup"><span data-stu-id="d69ef-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="d69ef-106">Если фильтры настроены неправильно, журналы могут содержать неверные данные.</span><span class="sxs-lookup"><span data-stu-id="d69ef-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="d69ef-107">Дополнительные сведения о фильтрации см. в разделе [Пошаговое руководство. Фильтрация выходных данных My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="d69ef-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="d69ef-108">Однако если журнал настроен неправильно, необходима дополнительная информация о его текущей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d69ef-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="d69ef-109">Эту информацию можно получить с помощью расширенного свойства журнала `TraceSource`.</span><span class="sxs-lookup"><span data-stu-id="d69ef-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="d69ef-110">Определение прослушивателей журнала для объекта Log в коде</span><span class="sxs-lookup"><span data-stu-id="d69ef-110">To determine the log listeners for the Log object in code</span></span>  
  
1. <span data-ttu-id="d69ef-111">Импортируйте пространство имен <xref:System.Diagnostics> в начало файла кода.</span><span class="sxs-lookup"><span data-stu-id="d69ef-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="d69ef-112">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="d69ef-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. <span data-ttu-id="d69ef-113">Создайте функцию, которая возвращает строку, состоящую из информации о каждом из прослушивателей журнала.</span><span class="sxs-lookup"><span data-stu-id="d69ef-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. <span data-ttu-id="d69ef-114">Передайте коллекцию прослушивателей журнала трассировки в функцию `GetListeners` и отобразите возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="d69ef-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     <span data-ttu-id="d69ef-115">Дополнительные сведения можно найти по адресу: <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="d69ef-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d69ef-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d69ef-116">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="d69ef-117">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="d69ef-117">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="d69ef-118">Пошаговое руководство: Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="d69ef-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
