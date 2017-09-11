---
title: "Запись сведений в журнал из приложения (Visual Basic)"
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
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
caps.latest.revision: 12
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
ms.openlocfilehash: 58f21df20425b0164586143ad5af6f363a90c3ef
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="logging-information-from-the-application-visual-basic"></a><span data-ttu-id="84b4f-102">Запись сведений в журнал из приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="84b4f-102">Logging Information from the Application (Visual Basic)</span></span>
<span data-ttu-id="84b4f-103">Этот раздел содержит сведения о том, как регистрировать в журнале информацию из приложения с помощью объектов `My.Application.Log` или `My.Log` и как расширить возможности ведения журнала в приложении.</span><span class="sxs-lookup"><span data-stu-id="84b4f-103">This section contains topics that cover how to log information from your application using the `My.Application.Log` or `My.Log` object, and how to extend the application's logging capabilities.</span></span>  
  
 <span data-ttu-id="84b4f-104">Объект `Log` предоставляет методы для записи информации в прослушиватели журнала приложения, а свойство `TraceSource` объекта `Log` предоставляет подробные сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="84b4f-104">The `Log` object provides methods for writing information to the application's log listeners, and the `Log` object's advanced `TraceSource` property provides detailed configuration information.</span></span> <span data-ttu-id="84b4f-105">Объект `Log` настраивается в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="84b4f-105">The `Log` object is configured by the application's configuration file.</span></span>  
  
 <span data-ttu-id="84b4f-106">Объект `My.Log` доступен только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="84b4f-106">The `My.Log` object is available only for ASP.NET applications.</span></span> <span data-ttu-id="84b4f-107">Для клиентских приложений следует использовать объект `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="84b4f-107">For client applications, use `My.Application.Log`.</span></span> <span data-ttu-id="84b4f-108">Для получения дополнительной информации см. <xref:Microsoft.VisualBasic.Logging.Log>.</span><span class="sxs-lookup"><span data-stu-id="84b4f-108">For more information, see <xref:Microsoft.VisualBasic.Logging.Log>.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="84b4f-109">Задачи</span><span class="sxs-lookup"><span data-stu-id="84b4f-109">Tasks</span></span>  
  
|<span data-ttu-id="84b4f-110">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="84b4f-110">To</span></span>|<span data-ttu-id="84b4f-111">См.</span><span class="sxs-lookup"><span data-stu-id="84b4f-111">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="84b4f-112">Запись информации о событиях в журналы приложения.</span><span class="sxs-lookup"><span data-stu-id="84b4f-112">Write event information to the application's logs.</span></span>|[<span data-ttu-id="84b4f-113">Практическое руководство. Запись сообщений в журнал</span><span class="sxs-lookup"><span data-stu-id="84b4f-113">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|<span data-ttu-id="84b4f-114">Запись информации об исключениях в журналы приложения.</span><span class="sxs-lookup"><span data-stu-id="84b4f-114">Write exception information to the application's logs.</span></span>|[<span data-ttu-id="84b4f-115">Практическое руководство. Запись в журнал сведений об исключениях</span><span class="sxs-lookup"><span data-stu-id="84b4f-115">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|<span data-ttu-id="84b4f-116">Запись данных трассировки в журналы приложения во время запуска и завершения работы приложения.</span><span class="sxs-lookup"><span data-stu-id="84b4f-116">Write trace information to the application's logs when the application starts and shuts down.</span></span>|[<span data-ttu-id="84b4f-117">Практическое руководство. Запись в журнал сообщений при запуске и завершении приложения</span><span class="sxs-lookup"><span data-stu-id="84b4f-117">How to: Log Messages When the Application Starts or Shuts Down</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|<span data-ttu-id="84b4f-118">Настройка объекта `My.Application.Log` для записи информации в текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="84b4f-118">Configure `My.Application.Log` to write information to a text file.</span></span>|[<span data-ttu-id="84b4f-119">Практическое руководство. Запись сведений о событиях в текстовый файл</span><span class="sxs-lookup"><span data-stu-id="84b4f-119">How to: Write Event Information to a Text File</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|<span data-ttu-id="84b4f-120">Настройка объекта `My.Application.Log` для записи информации в журнал событий.</span><span class="sxs-lookup"><span data-stu-id="84b4f-120">Configure `My.Application.Log` to write information to an event log.</span></span>|[<span data-ttu-id="84b4f-121">Практическое руководство. Запись в журнал событий приложения</span><span class="sxs-lookup"><span data-stu-id="84b4f-121">How to: Write to an Application Event Log</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|<span data-ttu-id="84b4f-122">Изменение места, в которое объект `My.Application.Log` записывает информацию.</span><span class="sxs-lookup"><span data-stu-id="84b4f-122">Change where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="84b4f-123">Пошаговое руководство. Изменение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="84b4f-123">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="84b4f-124">Выбор места, в которое объект `My.Application.Log` записывает информацию.</span><span class="sxs-lookup"><span data-stu-id="84b4f-124">Determine where `My.Application.Log` writes information.</span></span>|[<span data-ttu-id="84b4f-125">Пошаговое руководство. Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="84b4f-125">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|<span data-ttu-id="84b4f-126">Создание пользовательского прослушивателя журнала для `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="84b4f-126">Create a custom log listener for `My.Application.Log`.</span></span>|[<span data-ttu-id="84b4f-127">Пошаговое руководство. Создание пользовательских прослушивателей журнала</span><span class="sxs-lookup"><span data-stu-id="84b4f-127">Walkthrough: Creating Custom Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|<span data-ttu-id="84b4f-128">Фильтрация выходных данных журналов `My.Application.Log`.</span><span class="sxs-lookup"><span data-stu-id="84b4f-128">Filter the output of the `My.Application.Log` logs.</span></span>|[<span data-ttu-id="84b4f-129">Пошаговое руководство. Фильтрация вывода My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="84b4f-129">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a><span data-ttu-id="84b4f-130">См. также</span><span class="sxs-lookup"><span data-stu-id="84b4f-130">See Also</span></span>  
 <span data-ttu-id="84b4f-131"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="84b4f-131"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="84b4f-132">[Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="84b4f-132">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 [<span data-ttu-id="84b4f-133">Устранение неполадок, связанных с прослушивателями журнала</span><span class="sxs-lookup"><span data-stu-id="84b4f-133">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)

