---
title: Отслеживание рабочих процессов
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: f4ce25efae0e42fa7c95ce5dffe8da8e31db05a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="workflow-tracing"></a><span data-ttu-id="9d197-102">Отслеживание рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="9d197-102">Workflow Tracing</span></span>
<span data-ttu-id="9d197-103">Трассировка рабочего процесса позволяет получать сведения диагностики при помощи прослушивателей трассировки .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d197-103">Workflow tracing offers a way to capture diagnostic information using .NET Framework trace listeners.</span></span> <span data-ttu-id="9d197-104">Трассировку можно включить при обнаружении проблемы в работе приложения, а затем снова отключить после разрешения проблемы.</span><span class="sxs-lookup"><span data-stu-id="9d197-104">Tracing can be enabled if a problem is detected with the application and then disabled again once the problem is resolved.</span></span> <span data-ttu-id="9d197-105">Существует два способа включения трассировки отладки для рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="9d197-105">There are two ways you could enable debug tracing for workflows.</span></span> <span data-ttu-id="9d197-106">Можно настроить отслеживание в средстве просмотра трассировки событий либо использовать <xref:System.Diagnostics> для отправки событий трассировки в файл.</span><span class="sxs-lookup"><span data-stu-id="9d197-106">You can configure it using the Event Trace viewer or you can use <xref:System.Diagnostics> to send trace events to a file.</span></span>  
  
## <a name="enabling-debug-tracing-in-etw"></a><span data-ttu-id="9d197-107">Включение трассировки отладки в ETW</span><span class="sxs-lookup"><span data-stu-id="9d197-107">Enabling Debug Tracing in ETW</span></span>  
 <span data-ttu-id="9d197-108">Для включения трассировки при помощи ETW включите канал отладки в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="9d197-108">To enable tracing using ETW, enable the Debug channel in Event Viewer:</span></span>  
  
1.  <span data-ttu-id="9d197-109">Перейдите в узел аналитики и журналов отладки в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="9d197-109">Navigate to analytic and debug logs node in Event Viewer.</span></span>  
  
2.  <span data-ttu-id="9d197-110">В представлении дерева в средстве просмотра событий перейдите к **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="9d197-110">In the tree view in Event Viewer, navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="9d197-111">Щелкните правой кнопкой мыши **сервер приложений-приложения** и выберите **Просмотр -> Отобразить аналитический и отладочный журналы**.</span><span class="sxs-lookup"><span data-stu-id="9d197-111">Right-click **Application Server-Applications** and select **View->Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="9d197-112">Щелкните правой кнопкой мыши **отладки** и выберите **включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="9d197-112">Right-click **Debug** and select **Enable Log**.</span></span>  
  
3.  <span data-ttu-id="9d197-113">Когда рабочий процесс запускает отладку и трассы событий выдаются в канал отладки ETW, их можно просмотреть в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="9d197-113">When a workflow runs the debug and traces are emitted to ETW debug channel, they can be viewed in the Event Viewer.</span></span> <span data-ttu-id="9d197-114">Перейдите к **Просмотр событий -> приложений и журналы служб -> Майкрософт -> Windows -> сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="9d197-114">Navigate to **Event Viewer->Applications and Services Logs->Microsoft->Windows->Application Server-Applications**.</span></span> <span data-ttu-id="9d197-115">Щелкните правой кнопкой мыши **отладки** и выберите **обновление**.</span><span class="sxs-lookup"><span data-stu-id="9d197-115">Right-click **Debug** and select **Refresh**.</span></span>  
  
4.  <span data-ttu-id="9d197-116">Размер буфера аналитической трассировки по умолчанию составляет всего 4 килобайта (КБ). Рекомендуется увеличить этот размер до 32 КБ.</span><span class="sxs-lookup"><span data-stu-id="9d197-116">The default analytic trace buffer size is only 4 kilobytes (KB); it is recommended to increase the size to 32 KB.</span></span> <span data-ttu-id="9d197-117">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="9d197-117">To do this, perform the following steps.</span></span>  
  
    1.  <span data-ttu-id="9d197-118">Выполните следующую команду в текущем каталоге платформы (например, C:\Windows\Microsoft.NET\Framework\v4.0.21203):`wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="9d197-118">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
    2.  <span data-ttu-id="9d197-119">Изменение \<bufferSize > значение в файле Windows.ApplicationServer.Applications.man 32.</span><span class="sxs-lookup"><span data-stu-id="9d197-119">Change the \<bufferSize> value in the Windows.ApplicationServer.Applications.man file to 32.</span></span>  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3.  <span data-ttu-id="9d197-120">Выполните следующую команду в текущем каталоге платформы (например, C:\Windows\Microsoft.NET\Framework\v4.0.21203):`wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span><span class="sxs-lookup"><span data-stu-id="9d197-120">Execute the following command in the current framework directory (for example, C:\Windows\Microsoft.NET\Framework\v4.0.21203): `wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9d197-121">Если вы используете клиентский профиль .NET Framework 4, необходимо сначала зарегистрировать ETW-манифест, выполнив следующую команду из каталога .NET Framework 4: `ServiceModelReg.exe –i –c:etw`</span><span class="sxs-lookup"><span data-stu-id="9d197-121">If you are using the .NET Framework 4 Client Profile, you must first register the ETW manifest by running the following command from the .NET Framework 4 directory: `ServiceModelReg.exe –i –c:etw`</span></span>  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a><span data-ttu-id="9d197-122">Включение трассировки отладки при помощи System.Diagnostics</span><span class="sxs-lookup"><span data-stu-id="9d197-122">Enabling Debug Tracing using System.Diagnostics</span></span>  
 <span data-ttu-id="9d197-123">Эти прослушиватели можно настроить в файле App.config приложения рабочего процесса либо в файле Web.config для службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="9d197-123">These listeners can be configured in the App.config file of the workflow application, or the Web.config for a workflow service.</span></span> <span data-ttu-id="9d197-124">В этом примере [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) настроен для сохранения данных трассировки в файле MyTraceLog.txt в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9d197-124">In this example, a [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) is configured to save tracing information to the MyTraceLog.txt file in the current directory.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9d197-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9d197-125">See Also</span></span>  
 [<span data-ttu-id="9d197-126">Наблюдение за Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="9d197-126">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="9d197-127">Мониторинг приложений с</span><span class="sxs-lookup"><span data-stu-id="9d197-127">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
