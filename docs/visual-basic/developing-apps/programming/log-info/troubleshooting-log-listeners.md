---
title: "Устранение неполадок, связанных с прослушивателями журнала (Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
caps.latest.revision: 11
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0542aef4dc60821939e85760e6fadf0dfb528dec
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="f3107-102">Устранение неполадок, связанных с прослушивателями журнала (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3107-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="f3107-103">Объекты `My.Application.Log` и `My.Log` можно использовать для записи в журнал информации о событиях, происходящих в приложении.</span><span class="sxs-lookup"><span data-stu-id="f3107-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="f3107-104">Чтобы определить, какие прослушиватели журналов получают эти сообщения, см. раздел [Пошаговое руководство. Определение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="f3107-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="f3107-105">Объект `Log` может использовать фильтрацию журнала для ограничения объема данных, регистрируемых в журнале.</span><span class="sxs-lookup"><span data-stu-id="f3107-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="f3107-106">Если фильтры настроены неправильно, журналы могут содержать неверные данные.</span><span class="sxs-lookup"><span data-stu-id="f3107-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="f3107-107">Дополнительные сведения см. в разделе [Пошаговое руководство. Фильтрация вывода My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="f3107-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="f3107-108">Однако если журнал настроен неправильно, необходима дополнительная информация о его текущей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f3107-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="f3107-109">Эту информацию можно получить с помощью расширенного свойства журнала `TraceSource`.</span><span class="sxs-lookup"><span data-stu-id="f3107-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="f3107-110">Определение прослушивателей журнала для объекта Log в коде</span><span class="sxs-lookup"><span data-stu-id="f3107-110">To determine the log listeners for the Log object in code</span></span>  
  
1.  <span data-ttu-id="f3107-111">Импортируйте пространство имен <xref:System.Diagnostics> в начало файла кода.</span><span class="sxs-lookup"><span data-stu-id="f3107-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="f3107-112">Дополнительные сведения см. в статье [Оператор Imports (пространство имен .NET и тип)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span><span class="sxs-lookup"><span data-stu-id="f3107-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     <span data-ttu-id="f3107-113">[!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3107-113">[!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]</span></span>  
  
2.  <span data-ttu-id="f3107-114">Создайте функцию, которая возвращает строку, состоящую из информации о каждом из прослушивателей журнала.</span><span class="sxs-lookup"><span data-stu-id="f3107-114">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     <span data-ttu-id="f3107-115">[!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3107-115">[!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]</span></span>  
  
3.  <span data-ttu-id="f3107-116">Передайте коллекцию прослушивателей журнала трассировки в функцию `GetListeners` и отобразите возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="f3107-116">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     <span data-ttu-id="f3107-117">[!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3107-117">[!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]</span></span>  
  
     <span data-ttu-id="f3107-118">Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3107-118">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3107-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f3107-119">See Also</span></span>  
 <span data-ttu-id="f3107-120"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="f3107-120"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="f3107-121">[Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="f3107-121">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 [<span data-ttu-id="f3107-122">Пошаговое руководство. Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="f3107-122">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)

