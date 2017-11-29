---
title: "Устранение неполадок, связанных с прослушивателями журнала (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 14db7019415405af89e9f5e317da617debeb0a19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="a650f-102">Устранение неполадок, связанных с прослушивателями журнала (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a650f-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="a650f-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.</span><span class="sxs-lookup"><span data-stu-id="a650f-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="a650f-104">Чтобы определить, какие прослушиватели журналов получают эти сообщения, см. раздел [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="a650f-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="a650f-105">Объект `Log` может использовать фильтрацию журнала для ограничения объема данных, регистрируемых в журнале.</span><span class="sxs-lookup"><span data-stu-id="a650f-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="a650f-106">Если фильтры настроены неправильно, журналы могут содержать неверные данные.</span><span class="sxs-lookup"><span data-stu-id="a650f-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="a650f-107">Дополнительные сведения см. в разделе [Пошаговое руководство. Фильтрация вывода My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="a650f-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="a650f-108">Однако если журнал настроен неправильно, необходима дополнительная информация о его текущей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a650f-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="a650f-109">Эту информацию можно получить с помощью расширенного свойства журнала `TraceSource`.</span><span class="sxs-lookup"><span data-stu-id="a650f-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="a650f-110">Определение прослушивателей журнала для объекта Log в коде</span><span class="sxs-lookup"><span data-stu-id="a650f-110">To determine the log listeners for the Log object in code</span></span>  
  
1.  <span data-ttu-id="a650f-111">Импортируйте пространство имен <xref:System.Diagnostics> в начало файла кода.</span><span class="sxs-lookup"><span data-stu-id="a650f-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="a650f-112">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="a650f-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  <span data-ttu-id="a650f-113">Создайте функцию, которая возвращает строку, состоящую из информации о каждом из прослушивателей журнала.</span><span class="sxs-lookup"><span data-stu-id="a650f-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  <span data-ttu-id="a650f-114">Передайте коллекцию прослушивателей журнала трассировки в функцию `GetListeners` и отобразите возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="a650f-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     <span data-ttu-id="a650f-115">Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="a650f-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a650f-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a650f-116">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [<span data-ttu-id="a650f-117">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="a650f-117">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [<span data-ttu-id="a650f-118">Пошаговое руководство. Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="a650f-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
