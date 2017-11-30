---
title: "Отслеживание рабочих процессов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4332b93175f4cb751ba88c7d2b05e4b462de7748
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="workflow-tracing"></a><span data-ttu-id="f2509-102">Отслеживание рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="f2509-102">Workflow Tracing</span></span>
<span data-ttu-id="f2509-103">Трассировка рабочего процесса позволяет получать сведения диагностики при помощи прослушивателей трассировки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f2509-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="f2509-104">Трассировку можно включить при обнаружении проблемы в работе приложения, а затем снова отключить после разрешения проблемы.</span><span class="sxs-lookup"><span data-stu-id="f2509-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="f2509-105">Существует два способа включения трассировки отладки для рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="f2509-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="f2509-106">Можно настроить отслеживание в средстве просмотра трассировки событий либо использовать <xref:System.Diagnostics> для отправки событий трассировки в файл.</span><span class="sxs-lookup"><span data-stu-id="f2509-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="f2509-107">Включение трассировки отладки в ETW</span><span class="sxs-lookup"><span data-stu-id="f2509-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="f2509-108">Для включения трассировки при помощи ETW включите канал отладки в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f2509-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1.  <span data-ttu-id="f2509-109">Перейдите в узел аналитики и журналов отладки в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f2509-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2.  <span data-ttu-id="f2509-110">В представлении дерева в средстве просмотра событий перейдите к **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="f2509-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="f2509-111">Щелкните правой кнопкой мыши **сервер приложений-приложения** и выберите **Просмотр -> Отобразить аналитический и отладочный журналы**.</span><span class="sxs-lookup"><span data-stu-id="f2509-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="f2509-112">Щелкните правой кнопкой мыши **отладки** и выберите **включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="f2509-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3.  <span data-ttu-id="f2509-113">Когда рабочий процесс запускает отладку и трассы событий выдаются в канал отладки ETW, их можно просмотреть в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f2509-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="f2509-114">Перейдите к **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="f2509-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="f2509-115">Щелкните правой кнопкой мыши **отладки** и выберите **обновление**.</span><span class="sxs-lookup"><span data-stu-id="f2509-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4.  <span data-ttu-id="f2509-116">Размер буфера аналитической трассировки по умолчанию составляет всего 4 килобайта (КБ). Рекомендуется увеличить этот размер до 32 КБ.</span><span class="sxs-lookup"><span data-stu-id="f2509-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="f2509-117">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="f2509-117">To do this, perform the following steps.</span></span>  
  
    1.  <span data-ttu-id="f2509-118">Выполните следующую команду в текущем каталоге платформы (например, C:\Windows\Microsoft.NET\Framework\v4.0.21203):`wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="f2509-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2.  <span data-ttu-id="f2509-119">Изменение \<bufferSize > значение в файле Windows.ApplicationServer.Applications.man 32.</span><span class="sxs-lookup"><span data-stu-id="f2509-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  <span data-ttu-id="f2509-120">Выполните следующую команду в текущем каталоге платформы (например, C:\Windows\Microsoft.NET\Framework\v4.0.21203):`wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="f2509-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f2509-121">Если вы используете клиентский профиль .NET Framework 4, необходимо сначала зарегистрировать ETW-манифест, выполнив следующую команду из каталога .NET Framework 4:`ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="f2509-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="f2509-122">Включение трассировки отладки при помощи System.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="f2509-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="f2509-123">Эти прослушиватели можно настроить в файле App.config приложения рабочего процесса либо в файле Web.config для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f2509-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="f2509-124">В этом примере [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) настроен для сохранения данных трассировки в файле MyTraceLog.txt в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f2509-124">In this example, a [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="System.Activities" switchValue="Information">  
        <listeners>  
          <add name="textListener" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"  
           type="System.Diagnostics.TextWriterTraceListener"  
           initializeData="MyTraceLog.txt"  
           traceOutputOptions="ProcessId, DateTime" />  
    </sharedListeners>  
    <trace autoflush="true" indentsize="4">  
      <listeners>  
        <add name="textListener" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2509-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f2509-125">See Also</span></span>  
 [<span data-ttu-id="f2509-126">Наблюдение за Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="f2509-126">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="f2509-127">Мониторинг приложений с</span><span class="sxs-lookup"><span data-stu-id="f2509-127">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
