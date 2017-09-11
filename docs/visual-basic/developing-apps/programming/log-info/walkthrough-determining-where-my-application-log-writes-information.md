---
title: "Определение места записи информации для My.Application.Log (Visual Basic)"
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
- My.Log object, output location
- output, application log location
- My.Application.Log object, outpout location
- event logs, determining output location
- application event logs, output location
- applications [Visual Basic], output location
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36c91f607a5a9d0dcf65ee6e049b9a49cdd37929
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-determining-where-myapplicationlog-writes-information-visual-basic"></a><span data-ttu-id="5807d-102">Пошаговое руководство. Определение места записи информации для My.Application.Log (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5807d-102">Walkthrough: Determining Where My.Application.Log Writes Information (Visual Basic)</span></span>
<span data-ttu-id="5807d-103">Объект `My.Application.Log` может записывать информацию в несколько прослушивателей журналов.</span><span class="sxs-lookup"><span data-stu-id="5807d-103">The `My.Application.Log` object can write information to several log listeners.</span></span> <span data-ttu-id="5807d-104">Прослушиватели журнала настраиваются в файле конфигурации компьютера и могут переопределяться в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5807d-104">The log listeners are configured by the computer's configuration file and can be overridden by an application's configuration file.</span></span> <span data-ttu-id="5807d-105">В этом разделе описаны параметры по умолчанию и способ определения параметров для приложения.</span><span class="sxs-lookup"><span data-stu-id="5807d-105">This topic describes the default settings and how to determine the settings for your application.</span></span>  
  
 <span data-ttu-id="5807d-106">Дополнительные сведения о расположении выходных данных по умолчанию см. в разделе [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span><span class="sxs-lookup"><span data-stu-id="5807d-106">For more information about the default output locations, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>  
  
### <a name="to-determine-the-listeners-for-myapplicationlog"></a><span data-ttu-id="5807d-107">Определение прослушивателей для объекта My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="5807d-107">To determine the listeners for My.Application.Log</span></span>  
  
1.  <span data-ttu-id="5807d-108">Найдите файл конфигурации сборки.</span><span class="sxs-lookup"><span data-stu-id="5807d-108">Locate the assembly's configuration file.</span></span> <span data-ttu-id="5807d-109">Во время разработки сборки доступ к файлу app.config в [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] можно получить в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="5807d-109">If you are developing the assembly, you can access the app.config in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] from the **Solution Explorer**.</span></span> <span data-ttu-id="5807d-110">В противном случае имя файла конфигурации — это имя сборки с расширением .config, а расположен он в том же каталоге, что и сборка.</span><span class="sxs-lookup"><span data-stu-id="5807d-110">Otherwise, the configuration file name is the assembly's name appended with ".config", and it is located in the same directory as the assembly.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5807d-111">Не каждая сборка имеет файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5807d-111">Not every assembly has a configuration file.</span></span>  
  
     <span data-ttu-id="5807d-112">Файл конфигурации является XML-файлом.</span><span class="sxs-lookup"><span data-stu-id="5807d-112">The configuration file is an XML file.</span></span>  
  
2.  <span data-ttu-id="5807d-113">Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name` , равным DefaultSource, в разделе `<sources>` .</span><span class="sxs-lookup"><span data-stu-id="5807d-113">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="5807d-114">Раздел `<sources>` находится в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="5807d-114">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
     <span data-ttu-id="5807d-115">Если эти разделы не существуют, то настройка прослушивателей журнала `My.Application.Log` может быть задана в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="5807d-115">If these sections do not exist, then the computer's configuration file may configure the `My.Application.Log` log listeners.</span></span> <span data-ttu-id="5807d-116">Далее описано, как выяснить, что определяется в файле конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="5807d-116">The following steps describe how to determine what the computer configuration file defines:</span></span>  
  
    1.  <span data-ttu-id="5807d-117">Найдите файл machine.config компьютера.</span><span class="sxs-lookup"><span data-stu-id="5807d-117">Locate the computer's machine.config file.</span></span> <span data-ttu-id="5807d-118">Как правило, он находится в каталоге *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* , где `SystemRoot` — каталог операционной системы, а `frameworkVersion` — версия [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5807d-118">Typically, it is located in the *SystemRoot\Microsoft.NET\Framework\frameworkVersion\CONFIG* directory, where `SystemRoot` is the operating system directory, and `frameworkVersion` is the version of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
         <span data-ttu-id="5807d-119">Параметры в файле machine.config могут быть переопределены файлом конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5807d-119">The settings in machine.config can be overridden by an application's configuration file.</span></span>  
  
         <span data-ttu-id="5807d-120">Если необязательные элементы, перечисленные ниже, отсутствуют, их можно создать.</span><span class="sxs-lookup"><span data-stu-id="5807d-120">If the optional elements listed below do not exist, you can create them.</span></span>  
  
    2.  <span data-ttu-id="5807d-121">Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name` , равным DefaultSource, в разделе `<sources>` раздела `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="5807d-121">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", in the `<sources>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
         <span data-ttu-id="5807d-122">Если эти разделы не существуют, то в объекте `My.Application.Log` имеются только прослушиватели журнала по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5807d-122">If these sections do not exist, then the `My.Application.Log` has only the default log listeners.</span></span>  
  
3.  <span data-ttu-id="5807d-123">Найдите элементы <`add>` в разделе <`listeners>`.</span><span class="sxs-lookup"><span data-stu-id="5807d-123">Locate the <`add>` elements in the <`listeners>` section.</span></span>  
  
     <span data-ttu-id="5807d-124">Эти элементы добавляют именованные прослушиватели журнала в источник `My.Application.Log` .</span><span class="sxs-lookup"><span data-stu-id="5807d-124">These elements add the named log listeners to `My.Application.Log` source.</span></span>  
  
4.  <span data-ttu-id="5807d-125">Найдите элементы `<add>` с именами прослушивателей журнала в разделе `<sharedListeners>` раздела `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="5807d-125">Locate the `<add>` elements with the names of the log listeners in the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5.  <span data-ttu-id="5807d-126">Данные инициализации для многих типов общих прослушивателей включают описание того, куда прослушиватель направляет данные.</span><span class="sxs-lookup"><span data-stu-id="5807d-126">For many types of shared listeners, the listener's initialization data includes a description of where the listener directs the data:</span></span>  
  
    -   <span data-ttu-id="5807d-127">Прослушиватель <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> записывает данные в журнал файлов, как описано во введении.</span><span class="sxs-lookup"><span data-stu-id="5807d-127">A <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> listener writes to a file log, as described in the introduction.</span></span>  
  
    -   <span data-ttu-id="5807d-128">Прослушиватель <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> записывает данные в журнал событий компьютера, определяемый параметром `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="5807d-128">A <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> listener writes information to the computer event log specified by the `initializeData` parameter.</span></span> <span data-ttu-id="5807d-129">Для просмотра журнала событий можно использовать **обозреватель сервера** или **средство просмотра событий Windows**.</span><span class="sxs-lookup"><span data-stu-id="5807d-129">To view an event log, you can use **Server Explorer** or **Windows Event Viewer**.</span></span> <span data-ttu-id="5807d-130">Для получения дополнительной информации см. [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span><span class="sxs-lookup"><span data-stu-id="5807d-130">For more information, see [ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299).</span></span>  
  
    -   <span data-ttu-id="5807d-131">Прослушиватели <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> и <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> записывают данные в файл, указанный в параметре `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="5807d-131">The <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> and <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> listeners write to the file specified in the `initializeData` parameter.</span></span>  
  
    -   <span data-ttu-id="5807d-132">Прослушиватель <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> выводит данные в консоль командной строки.</span><span class="sxs-lookup"><span data-stu-id="5807d-132">A <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> listener writes to the command-line console.</span></span>  
  
    -   <span data-ttu-id="5807d-133">Сведения о том, куда записывают информацию другие типы прослушивателей журналов, приведены в документации по этим типам.</span><span class="sxs-lookup"><span data-stu-id="5807d-133">For information about where other types of log listeners write information, consult that type's documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5807d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5807d-134">See Also</span></span>  
 <span data-ttu-id="5807d-135"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5807d-135"><xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName></span></span>   
 <span data-ttu-id="5807d-136"><xref:System.Diagnostics.DefaultTraceListener></span><span class="sxs-lookup"><span data-stu-id="5807d-136"><xref:System.Diagnostics.DefaultTraceListener></span></span>   
 <span data-ttu-id="5807d-137"><xref:System.Diagnostics.EventLogTraceListener></span><span class="sxs-lookup"><span data-stu-id="5807d-137"><xref:System.Diagnostics.EventLogTraceListener></span></span>   
 <span data-ttu-id="5807d-138"><xref:System.Diagnostics.DelimitedListTraceListener></span><span class="sxs-lookup"><span data-stu-id="5807d-138"><xref:System.Diagnostics.DelimitedListTraceListener></span></span>   
 <span data-ttu-id="5807d-139"><xref:System.Diagnostics.XmlWriterTraceListener></span><span class="sxs-lookup"><span data-stu-id="5807d-139"><xref:System.Diagnostics.XmlWriterTraceListener></span></span>   
 <span data-ttu-id="5807d-140"><xref:System.Diagnostics.ConsoleTraceListener></span><span class="sxs-lookup"><span data-stu-id="5807d-140"><xref:System.Diagnostics.ConsoleTraceListener></span></span>   
 <span data-ttu-id="5807d-141"><xref:System.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="5807d-141"><xref:System.Diagnostics></span></span>   
 <span data-ttu-id="5807d-142">[Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span><span class="sxs-lookup"><span data-stu-id="5807d-142">[Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md) </span></span>  
 <span data-ttu-id="5807d-143">[Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="5807d-143">[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md) </span></span>  
 <span data-ttu-id="5807d-144">[Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span><span class="sxs-lookup"><span data-stu-id="5807d-144">[How to: Write Log Messages](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md) </span></span>  
 <span data-ttu-id="5807d-145">[Пошаговое руководство. Изменение места записи сведений для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span><span class="sxs-lookup"><span data-stu-id="5807d-145">[Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md) </span></span>  
 <span data-ttu-id="5807d-146">[События трассировки событий Windows в .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299) </span><span class="sxs-lookup"><span data-stu-id="5807d-146">[ETW Events in the .NET Framework](http://msdn.microsoft.com/library/d186276f-6afb-4dfd-bf3c-4251edc2c299) </span></span>  
 [<span data-ttu-id="5807d-147">Устранение неполадок, связанных с прослушивателями журнала</span><span class="sxs-lookup"><span data-stu-id="5807d-147">Troubleshooting: Log Listeners</span></span>](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)

