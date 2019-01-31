---
title: Как выполнить Запись в журнал событий приложения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
ms.openlocfilehash: 78d7fbd7aa5cb0062a51145725a6fc2e9dce7525
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662638"
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a><span data-ttu-id="47a1d-102">Как выполнить Запись в журнал событий приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47a1d-102">How to: Write to an Application Event Log (Visual Basic)</span></span>
<span data-ttu-id="47a1d-103">Для записи информации о событиях, возникающих в приложении, можно использовать объекты `My.Application.Log` и `My.Log` .</span><span class="sxs-lookup"><span data-stu-id="47a1d-103">You can use the `My.Application.Log` and `My.Log` objects to write information about events that occur in your application.</span></span> <span data-ttu-id="47a1d-104">В этом примере показано, как настроить прослушиватель журнала событий, чтобы объект `My.Application.Log` записывал данные трассировки в журнал событий приложения.</span><span class="sxs-lookup"><span data-stu-id="47a1d-104">This example shows how to configure an event log listener so `My.Application.Log` writes tracing information to the Application event log.</span></span>  
  
 <span data-ttu-id="47a1d-105">Запись в журнал безопасности невозможна.</span><span class="sxs-lookup"><span data-stu-id="47a1d-105">You cannot write to the Security log.</span></span> <span data-ttu-id="47a1d-106">Для записи в системный журнал необходимо быть членом учетной записи LocalSystem или "Администратор".</span><span class="sxs-lookup"><span data-stu-id="47a1d-106">In order to write to the System log, you must be a member of the LocalSystem or Administrator account.</span></span>  
  
 <span data-ttu-id="47a1d-107">Для просмотра журнала событий можно использовать **обозреватель сервера** или **средство просмотра событий Windows**.</span><span class="sxs-lookup"><span data-stu-id="47a1d-107">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="47a1d-108">Дополнительные сведения см. в разделе [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="47a1d-108">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47a1d-109">Журналы событий не поддерживаются в Windows 95, Windows 98 и Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="47a1d-109">Event logs are not supported on Windows 95, Windows 98, or Windows Millennium Edition.</span></span>  
  
### <a name="to-add-and-configure-the-event-log-listener"></a><span data-ttu-id="47a1d-110">Добавление и настройка прослушивателя журнала событий</span><span class="sxs-lookup"><span data-stu-id="47a1d-110">To add and configure the event log listener</span></span>  
  
1.  <span data-ttu-id="47a1d-111">Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="47a1d-111">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="47a1d-112">\- или -</span><span class="sxs-lookup"><span data-stu-id="47a1d-112">\- or -</span></span>  
  
     <span data-ttu-id="47a1d-113">Если файл app.config отсутствует, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="47a1d-113">If there is no app.config file,</span></span>  
  
    1.  <span data-ttu-id="47a1d-114">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="47a1d-114">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="47a1d-115">В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.</span><span class="sxs-lookup"><span data-stu-id="47a1d-115">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="47a1d-116">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="47a1d-116">Click **Add**.</span></span>  
  
2.  <span data-ttu-id="47a1d-117">Найдите раздел `<listeners>` в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="47a1d-117">Locate the `<listeners>` section in the application configuration file.</span></span>  
  
     <span data-ttu-id="47a1d-118">Вы найдете раздел `<listeners>` в разделе `<source>` с атрибутом имени DefaultSource, вложенным в раздел `<system.diagnostics>` , который, в свою очередь, вложен в раздел `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="47a1d-118">You will find the `<listeners>` section in the `<source>` section with the name attribute "DefaultSource", which is nested under the `<system.diagnostics>` section, which is nested under the top-level `<configuration>` section.</span></span>  
  
3.  <span data-ttu-id="47a1d-119">Добавьте в этот раздел `<listeners>` следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="47a1d-119">Add this element to that `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="EventLog"/>  
    ```  
  
4.  <span data-ttu-id="47a1d-120">Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="47a1d-120">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="47a1d-121">Добавьте в этот раздел `<sharedListeners>` следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="47a1d-121">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="EventLog"  
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
         initializeData="APPLICATION_NAME"/>  
    ```  
  
     <span data-ttu-id="47a1d-122">Замените `APPLICATION_NAME` именем приложения.</span><span class="sxs-lookup"><span data-stu-id="47a1d-122">Replace `APPLICATION_NAME` with the name of your application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47a1d-123">Как правило, приложение записывает в журнал событий только ошибки.</span><span class="sxs-lookup"><span data-stu-id="47a1d-123">Typically, an application writes only errors to the event log.</span></span> <span data-ttu-id="47a1d-124">Сведения о фильтрации выходных данных журнала см. в разделе [Практическое руководство. Фильтрация выходных данных My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="47a1d-124">For information on filtering log output, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
### <a name="to-write-event-information-to-the-event-log"></a><span data-ttu-id="47a1d-125">Запись информации о событии в журнал событий</span><span class="sxs-lookup"><span data-stu-id="47a1d-125">To write event information to the event log</span></span>  
  
-   <span data-ttu-id="47a1d-126">Для записи информации в журнал событий используйте метод `My.Application.Log.WriteEntry` или `My.Application.Log.WriteException` .</span><span class="sxs-lookup"><span data-stu-id="47a1d-126">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the event log.</span></span> <span data-ttu-id="47a1d-127">Дополнительные сведения см. в разделе [Как Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) и [Практическое руководство. Исключения журналов](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="47a1d-127">For more information, see [How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) and [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>  
  
     <span data-ttu-id="47a1d-128">После настройки прослушивателя журнала событий для сборки он получает все сообщения, которые записываются объектом `My.Applcation.Log` из этой сборки.</span><span class="sxs-lookup"><span data-stu-id="47a1d-128">After you configure the event log listener for an assembly, it receives all messages that `My.Applcation.Log` writes from that assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47a1d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="47a1d-129">See also</span></span>
- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="47a1d-130">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="47a1d-130">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="47a1d-131">Практическое руководство. Исплючения журналов</span><span class="sxs-lookup"><span data-stu-id="47a1d-131">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="47a1d-132">Пошаговое руководство: Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="47a1d-132">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
