---
title: Практическое руководство. Запись в журнал событий приложения
ms.date: 07/20/2015
helpviewer_keywords:
- Computer.EventLog element
- WriteEntry method [Visual Basic]
- My.Computer.EventLog element
- event logs, writing to
ms.assetid: cadbc8c1-87af-4746-934e-55b79a4f6e2b
ms.openlocfilehash: 511bb8fb16851872c1a16ae7627ed0fc6594337c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "74352048"
---
# <a name="how-to-write-to-an-application-event-log-visual-basic"></a><span data-ttu-id="91d55-102">Практическое руководство. Запись в журнал событий приложения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91d55-102">How to: Write to an Application Event Log (Visual Basic)</span></span>

<span data-ttu-id="91d55-103">Для записи информации о событиях, возникающих в приложении, можно использовать объекты `My.Application.Log` и `My.Log` .</span><span class="sxs-lookup"><span data-stu-id="91d55-103">You can use the `My.Application.Log` and `My.Log` objects to write information about events that occur in your application.</span></span> <span data-ttu-id="91d55-104">В этом примере показано, как настроить прослушиватель журнала событий, чтобы объект `My.Application.Log` записывал данные трассировки в журнал событий приложения.</span><span class="sxs-lookup"><span data-stu-id="91d55-104">This example shows how to configure an event log listener so `My.Application.Log` writes tracing information to the Application event log.</span></span>

<span data-ttu-id="91d55-105">Запись в журнал безопасности невозможна.</span><span class="sxs-lookup"><span data-stu-id="91d55-105">You cannot write to the Security log.</span></span> <span data-ttu-id="91d55-106">Для записи в системный журнал необходимо быть членом учетной записи LocalSystem или "Администратор".</span><span class="sxs-lookup"><span data-stu-id="91d55-106">In order to write to the System log, you must be a member of the LocalSystem or Administrator account.</span></span>

<span data-ttu-id="91d55-107">Для просмотра журнала событий можно использовать **обозреватель сервера** или **средство просмотра событий Windows**.</span><span class="sxs-lookup"><span data-stu-id="91d55-107">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="91d55-108">Для получения дополнительной информации см. [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="91d55-108">For more information, see [ETW Events in the .NET Framework](../../../../framework/performance/etw-events.md).</span></span>

## <a name="to-add-and-configure-the-event-log-listener"></a><span data-ttu-id="91d55-109">Добавление и настройка прослушивателя журнала событий</span><span class="sxs-lookup"><span data-stu-id="91d55-109">To add and configure the event log listener</span></span>

1. <span data-ttu-id="91d55-110">Щелкните правой кнопкой мыши файл app.config в **обозревателе решений** и выберите команду **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="91d55-110">Right-click app.config in **Solution Explorer** and choose **Open**.</span></span>

    <span data-ttu-id="91d55-111">\- или -</span><span class="sxs-lookup"><span data-stu-id="91d55-111">\- or -</span></span>

    <span data-ttu-id="91d55-112">Если файл app.config отсутствует, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="91d55-112">If there is no app.config file,</span></span>

    1. <span data-ttu-id="91d55-113">В меню **Проект** выберите пункт **Добавить новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="91d55-113">On the **Project** menu, choose **Add New Item**.</span></span>

    2. <span data-ttu-id="91d55-114">В диалоговом окне **Добавление нового элемента** выберите элемент **Файл конфигурации приложения**.</span><span class="sxs-lookup"><span data-stu-id="91d55-114">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>

    3. <span data-ttu-id="91d55-115">Нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="91d55-115">Click **Add**.</span></span>

2. <span data-ttu-id="91d55-116">Найдите раздел `<listeners>` в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="91d55-116">Locate the `<listeners>` section in the application configuration file.</span></span>

    <span data-ttu-id="91d55-117">Вы найдете раздел `<listeners>` в разделе `<source>` с атрибутом имени DefaultSource, вложенным в раздел `<system.diagnostics>` , который, в свою очередь, вложен в раздел `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="91d55-117">You will find the `<listeners>` section in the `<source>` section with the name attribute "DefaultSource", which is nested under the `<system.diagnostics>` section, which is nested under the top-level `<configuration>` section.</span></span>

3. <span data-ttu-id="91d55-118">Добавьте в этот раздел `<listeners>` следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="91d55-118">Add this element to that `<listeners>` section:</span></span>

    ```xml
    <add name="EventLog"/>
    ```

4. <span data-ttu-id="91d55-119">Найдите раздел `<sharedListeners>` в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="91d55-119">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>

5. <span data-ttu-id="91d55-120">Добавьте в этот раздел `<sharedListeners>` следующий элемент:</span><span class="sxs-lookup"><span data-stu-id="91d55-120">Add this element to that `<sharedListeners>` section:</span></span>

    ```xml
    <add name="EventLog"
        type="System.Diagnostics.EventLogTraceListener, System, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
         initializeData="APPLICATION_NAME"/>
    ```

    <span data-ttu-id="91d55-121">Замените `APPLICATION_NAME` именем приложения.</span><span class="sxs-lookup"><span data-stu-id="91d55-121">Replace `APPLICATION_NAME` with the name of your application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="91d55-122">Как правило, приложение записывает в журнал событий только ошибки.</span><span class="sxs-lookup"><span data-stu-id="91d55-122">Typically, an application writes only errors to the event log.</span></span> <span data-ttu-id="91d55-123">Сведения о фильтрации выходных данных журнала см. в разделе [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="91d55-123">For information on filtering log output, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>

## <a name="to-write-event-information-to-the-event-log"></a><span data-ttu-id="91d55-124">Запись информации о событии в журнал событий</span><span class="sxs-lookup"><span data-stu-id="91d55-124">To write event information to the event log</span></span>

<span data-ttu-id="91d55-125">Для записи информации в журнал событий используйте метод `My.Application.Log.WriteEntry` или `My.Application.Log.WriteException` .</span><span class="sxs-lookup"><span data-stu-id="91d55-125">Use the `My.Application.Log.WriteEntry` or `My.Application.Log.WriteException` method to write information to the event log.</span></span> <span data-ttu-id="91d55-126">Дополнительные сведения см. в разделах [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) и [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="91d55-126">For more information, see [How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) and [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>

<span data-ttu-id="91d55-127">После настройки прослушивателя журнала событий для сборки он получает все сообщения, которые записываются объектом `My.Application.Log` из этой сборки.</span><span class="sxs-lookup"><span data-stu-id="91d55-127">After you configure the event log listener for an assembly, it receives all messages that `My.Application.Log` writes from that assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="91d55-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="91d55-128">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="91d55-129">Работа с журналами приложения</span><span class="sxs-lookup"><span data-stu-id="91d55-129">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="91d55-130">Практическое руководство. Запись в журнал сведений об исключениях</span><span class="sxs-lookup"><span data-stu-id="91d55-130">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="91d55-131">Пошаговое руководство. Определение места записи сведений для My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="91d55-131">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
