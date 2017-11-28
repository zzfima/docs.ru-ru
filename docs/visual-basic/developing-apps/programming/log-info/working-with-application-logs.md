---
title: "Работа с журналами приложения в Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea5f3699ca5a1b6b0859ac266656deb933839d3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="working-with-application-logs-in-visual-basic"></a><span data-ttu-id="26aaf-102">Работа с журналами приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26aaf-102">Working with Application Logs in Visual Basic</span></span>
<span data-ttu-id="26aaf-103">Объекты `My.Applicaton.Log` и `My.Log` упрощают запись сообщений и данных трассировки в журналы.</span><span class="sxs-lookup"><span data-stu-id="26aaf-103">The `My.Applicaton.Log` and `My.Log` objects make it easy to write logging and tracing information to logs.</span></span>  
  
## <a name="how-messages-are-logged"></a><span data-ttu-id="26aaf-104">Как осуществляется регистрация сообщений</span><span class="sxs-lookup"><span data-stu-id="26aaf-104">How Messages are Logged</span></span>  
 <span data-ttu-id="26aaf-105">Сначала проверяется уровень серьезности сообщения с помощью свойства <xref:System.Diagnostics.TraceSource.Switch%2A> свойства журнала <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> .</span><span class="sxs-lookup"><span data-stu-id="26aaf-105">First, the severity of the message is checked with the <xref:System.Diagnostics.TraceSource.Switch%2A> property of the log's <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> property.</span></span> <span data-ttu-id="26aaf-106">По умолчанию только сообщения с уровнем серьезности "Информация" и более высоким передаются прослушивателям трассировки, определенным в коллекции `TraceListener` журнала.</span><span class="sxs-lookup"><span data-stu-id="26aaf-106">By default, only messages of severity "Information" and higher are passed on to the trace listeners, specified in the log's `TraceListener` collection.</span></span> <span data-ttu-id="26aaf-107">Затем каждый прослушиватель сравнивает серьезность сообщения со свойством <xref:System.Diagnostics.TraceSource.Switch%2A> прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="26aaf-107">Then, each listener compares the severity of the message to the listener's <xref:System.Diagnostics.TraceSource.Switch%2A> property.</span></span> <span data-ttu-id="26aaf-108">Если уровень серьезности сообщения достаточно высокий, прослушиватель записывает сообщение.</span><span class="sxs-lookup"><span data-stu-id="26aaf-108">If the message's severity is high enough, the listener writes out the message.</span></span>  
  
 <span data-ttu-id="26aaf-109">На приведенной ниже схеме показан способ передачи сообщения, записанного методом `WriteEntry` , в методы `WriteLine` прослушивателей трассировки журнала.</span><span class="sxs-lookup"><span data-stu-id="26aaf-109">The following diagram shows how a message written to the `WriteEntry` method gets passed to the `WriteLine` methods of the log's trace listeners:</span></span>  
  
 <span data-ttu-id="26aaf-110">![Вызов журнала My](../../../../visual-basic/developing-apps/programming/log-info/media/mylogcall.png "MyLogCall")</span><span class="sxs-lookup"><span data-stu-id="26aaf-110">![My Log Call](../../../../visual-basic/developing-apps/programming/log-info/media/mylogcall.png "MyLogCall")</span></span>  
  
 <span data-ttu-id="26aaf-111">Поведение журнала и прослушивателей трассировки можно изменить путем изменения файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="26aaf-111">You can change the behavior of the log and the trace listeners by changing the application's configuration file.</span></span> <span data-ttu-id="26aaf-112">На приведенной ниже схеме показано соответствие между элементами журнала и файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="26aaf-112">The following diagram shows the correspondence between the parts of the log and the configuration file.</span></span>  
  
 <span data-ttu-id="26aaf-113">![Конфигурация журнала My](../../../../visual-basic/developing-apps/programming/log-info/media/mylogconfig.png "MyLogConfig")</span><span class="sxs-lookup"><span data-stu-id="26aaf-113">![My Log Configuration](../../../../visual-basic/developing-apps/programming/log-info/media/mylogconfig.png "MyLogConfig")</span></span>  
  
## <a name="where-messages-are-logged"></a><span data-ttu-id="26aaf-114">Куда записываются сообщения</span><span class="sxs-lookup"><span data-stu-id="26aaf-114">Where Messages are Logged</span></span>  
 <span data-ttu-id="26aaf-115">Если сборка не имеет файла конфигурации, объекты `My.Application.Log` и `My.Log` записывают сообщения в вывод отладки приложения (с использованием класса <xref:System.Diagnostics.DefaultTraceListener> ).</span><span class="sxs-lookup"><span data-stu-id="26aaf-115">If the assembly has no configuration file, the `My.Application.Log` and `My.Log` objects write to the application's debug output (through the <xref:System.Diagnostics.DefaultTraceListener> class).</span></span> <span data-ttu-id="26aaf-116">Кроме того, объект `My.Application.Log` записывает данные в файл журнала сборки (с использованием класса <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>), а объект `My.Log` записывает сообщения в вывод веб-страницы ASP.NET (с использованием класса <xref:System.Web.WebPageTraceListener>).</span><span class="sxs-lookup"><span data-stu-id="26aaf-116">In addition, the `My.Application.Log` object writes to the assembly's log file (through the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class), while the `My.Log` object writes to the ASP.NET Web page's output (through the <xref:System.Web.WebPageTraceListener> class).</span></span>  
  
 <span data-ttu-id="26aaf-117">При работе с приложением в режиме отладки вывод отладки можно просматривать в окне [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] **Output** window when running your application in debug mode.</span><span class="sxs-lookup"><span data-stu-id="26aaf-117">The debug output can be viewed in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] **Output** window when running your application in debug mode.</span></span> <span data-ttu-id="26aaf-118">Чтобы открыть окно **Вывод** , выберите пункт меню **Отладка** , наведите указатель на пункт **Окна**и выберите пункт **Вывод**.</span><span class="sxs-lookup"><span data-stu-id="26aaf-118">To open the **Output** window, click the **Debug** menu item, point to **Windows**, and then click **Output**.</span></span> <span data-ttu-id="26aaf-119">В окне **Вывод** выберите значение **Отладка** в поле **Показать выходные данные из** .</span><span class="sxs-lookup"><span data-stu-id="26aaf-119">In the **Output** window, select **Debug** from the **Show output from** box.</span></span>  
  
 <span data-ttu-id="26aaf-120">По умолчанию объект `My.Application.Log` записывает сообщения в файл журнала, расположенный по пути данных приложения пользователя.</span><span class="sxs-lookup"><span data-stu-id="26aaf-120">By default, `My.Application.Log` writes the log file in the path for the user's application data.</span></span> <span data-ttu-id="26aaf-121">Путь можно получить из свойства <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> объекта <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> .</span><span class="sxs-lookup"><span data-stu-id="26aaf-121">You can get the path from the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> property of the <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> object.</span></span> <span data-ttu-id="26aaf-122">Путь имеет следующий формат:</span><span class="sxs-lookup"><span data-stu-id="26aaf-122">The format of that path is as follows:</span></span>  
  
 `BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`  
  
 <span data-ttu-id="26aaf-123">Стандартное значение для `BasePath` будет следующим.</span><span class="sxs-lookup"><span data-stu-id="26aaf-123">A typical value for `BasePath` is as follows.</span></span>  
  
 <span data-ttu-id="26aaf-124">C:\Documents and Settings\\`username`\Application Data</span><span class="sxs-lookup"><span data-stu-id="26aaf-124">C:\Documents and Settings\\`username`\Application Data</span></span>  
  
 <span data-ttu-id="26aaf-125">Значения параметров `CompanyName`, `ProductName`и `ProductVersion` берутся из сведений о сборке приложения.</span><span class="sxs-lookup"><span data-stu-id="26aaf-125">The values of `CompanyName`, `ProductName`, and `ProductVersion` come from the application's assembly information.</span></span> <span data-ttu-id="26aaf-126">Имя файла журнала имеет следующий формат: *AssemblyName*.log, где *AssemblyName* — имя файла сборки без расширения.</span><span class="sxs-lookup"><span data-stu-id="26aaf-126">The form of the log file name is *AssemblyName*.log, where *AssemblyName* is the file name of the assembly without the extension.</span></span> <span data-ttu-id="26aaf-127">Если требуется несколько файлов журнала, например, когда исходный журнал недоступен при попытке записи в журнал, имя файла журнала имеет следующий формат: *AssemblyName*-*iteration*.log, где `iteration` — положительное целое число типа `Integer`.</span><span class="sxs-lookup"><span data-stu-id="26aaf-127">If more than one log file is needed, such as when the original log is unavailable when the application attempts to write to the log, the form for the log file name is *AssemblyName*-*iteration*.log, where `iteration` is a positive `Integer`.</span></span>  
  
 <span data-ttu-id="26aaf-128">Поведение по умолчанию можно переопределить путем добавления или изменения файлов конфигурации компьютера и приложения.</span><span class="sxs-lookup"><span data-stu-id="26aaf-128">You can override the default behavior by adding or changing the computer's and the application's configuration files.</span></span> <span data-ttu-id="26aaf-129">Для получения дополнительной информации см. [Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="26aaf-129">For more information, see [Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md).</span></span>  
  
## <a name="configuring-log-settings"></a><span data-ttu-id="26aaf-130">Настройка параметров журнала</span><span class="sxs-lookup"><span data-stu-id="26aaf-130">Configuring Log Settings</span></span>  
 <span data-ttu-id="26aaf-131">Реализация объекта `Log` по умолчанию работает без файла конфигурации приложения app.config. Чтобы изменить значения по умолчанию, необходимо добавить файл конфигурации с новыми значениями параметров.</span><span class="sxs-lookup"><span data-stu-id="26aaf-131">The `Log` object has a default implementation that works without an application configuration file, app.config. To change the defaults, you must add a configuration file with the new settings.</span></span> <span data-ttu-id="26aaf-132">Дополнительные сведения см. в разделе [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="26aaf-132">For more information, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="26aaf-133">Разделы конфигурации журнала находятся в узле `<system.diagnostics>` в основном узле `<configuration>` файла app.config.</span><span class="sxs-lookup"><span data-stu-id="26aaf-133">The log configuration sections are located in the `<system.diagnostics>` node in the main `<configuration>` node of the app.config file.</span></span> <span data-ttu-id="26aaf-134">Сведения журнала определены в нескольких узлах.</span><span class="sxs-lookup"><span data-stu-id="26aaf-134">Log information is defined in several nodes:</span></span>  
  
-   <span data-ttu-id="26aaf-135">Прослушиватели для объекта `Log` определены в узле `<sources>` с именем DefaultSource.</span><span class="sxs-lookup"><span data-stu-id="26aaf-135">The listeners for the `Log` object are defined in the `<sources>` node named DefaultSource.</span></span>  
  
-   <span data-ttu-id="26aaf-136">Фильтр серьезности для объекта `Log` определен в узле `<switches>` с именем DefaultSwitch.</span><span class="sxs-lookup"><span data-stu-id="26aaf-136">The severity filter for the `Log` object is defined in the `<switches>` node named DefaultSwitch.</span></span>  
  
-   <span data-ttu-id="26aaf-137">Прослушиватели журнала определены в узле `<sharedListeners>` .</span><span class="sxs-lookup"><span data-stu-id="26aaf-137">The log listeners are defined in the `<sharedListeners>` node.</span></span>  
  
 <span data-ttu-id="26aaf-138">Примеры узлов `<sources>`, `<switches>`и `<sharedListeners>` показаны в приведенном ниже коде.</span><span class="sxs-lookup"><span data-stu-id="26aaf-138">Examples of `<sources>`, `<switches>`, and `<sharedListeners>` nodes are shown in the following code:</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="DefaultSource" switchName="DefaultSwitch">  
        <listeners>  
          <add name="FileLog"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="DefaultSwitch" value="Information" />  
    </switches>  
    <sharedListeners>  
      <add name="FileLog"  
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,  
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"  
        initializeData="FileLogWriter"  
      />  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="changing-log-settings-after-deployment"></a><span data-ttu-id="26aaf-139">Изменение параметров журнала после развертывания</span><span class="sxs-lookup"><span data-stu-id="26aaf-139">Changing Log Settings after Deployment</span></span>  
 <span data-ttu-id="26aaf-140">При разработке приложения его параметры конфигурации хранятся в файле app.config, как показано в приведенных выше примерах.</span><span class="sxs-lookup"><span data-stu-id="26aaf-140">When you develop an application, its configuration settings are stored in the app.config file, as shown in the examples above.</span></span> <span data-ttu-id="26aaf-141">После развертывания приложения настройку журнала можно по-прежнему выполнять с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="26aaf-141">After you deploy your application, you can still configure the log by editing the configuration file.</span></span> <span data-ttu-id="26aaf-142">В приложении Windows этот файл имеет имя *имяПриложения*.exe.config и должен находиться в той же папке, что и исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="26aaf-142">In a Windows-based application, this file's name is *applicationName*.exe.config, and it must reside in the same folder as the executable file.</span></span> <span data-ttu-id="26aaf-143">Для веб-приложения это файл Web.config, связанный с проектом.</span><span class="sxs-lookup"><span data-stu-id="26aaf-143">For a Web application, this is the Web.config file associated with the project.</span></span>  
  
 <span data-ttu-id="26aaf-144">Когда приложение выполняет код, который впервые создает экземпляр класса, выполняется проверка сведений об объекте в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="26aaf-144">When your application executes the code that creates an instance of a class for the first time, it checks the configuration file for information about the object.</span></span> <span data-ttu-id="26aaf-145">Для объекта `Log` это происходит при первом обращении к объекту `Log` .</span><span class="sxs-lookup"><span data-stu-id="26aaf-145">For the `Log` object, this happens the first time the `Log` object is accessed.</span></span> <span data-ttu-id="26aaf-146">Система проверяет файл конфигурации только один раз для каждого отдельного объекта — при первом создании объекта в приложении.</span><span class="sxs-lookup"><span data-stu-id="26aaf-146">The system examines the configuration file only once for any particular object—the first time your application creates the object.</span></span> <span data-ttu-id="26aaf-147">Таким образом, необходимо перезапустить приложение, чтобы изменения вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="26aaf-147">Therefore, you may need to restart the application for the changes to take effect.</span></span>  
  
 <span data-ttu-id="26aaf-148">В развернутом приложении активация кода трассировки выполняется путем повторной настройки объектов переключателей до запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="26aaf-148">In a deployed application, you enable trace code by reconfiguring switch objects before your application starts.</span></span> <span data-ttu-id="26aaf-149">Обычно это подразумевает включение и отключение объектов переключателей или изменение уровней трассировки, а затем перезапуск приложения.</span><span class="sxs-lookup"><span data-stu-id="26aaf-149">Typically, this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="26aaf-150">Вопросы безопасности</span><span class="sxs-lookup"><span data-stu-id="26aaf-150">Security Considerations</span></span>  
 <span data-ttu-id="26aaf-151">При записи данных в журнал необходимо учитывать указанные ниже моменты.</span><span class="sxs-lookup"><span data-stu-id="26aaf-151">Consider the following when writing data to the log:</span></span>  
  
-   <span data-ttu-id="26aaf-152">**Не допускайте утечки сведений о пользователе**</span><span class="sxs-lookup"><span data-stu-id="26aaf-152">**Avoid leaking user information.**</span></span> <span data-ttu-id="26aaf-153">. Записывайте в журнал только одобренные сведения.</span><span class="sxs-lookup"><span data-stu-id="26aaf-153">Ensure that your application writes only approved information to the log.</span></span> <span data-ttu-id="26aaf-154">Например, в журнале приложения могут содержаться имена пользователей, но не их пароли.</span><span class="sxs-lookup"><span data-stu-id="26aaf-154">For example, it may be acceptable for the application log to contain user names, but not user passwords.</span></span>  
  
-   <span data-ttu-id="26aaf-155">**Храните журнал в безопасном месте**</span><span class="sxs-lookup"><span data-stu-id="26aaf-155">**Make log locations secure.**</span></span> <span data-ttu-id="26aaf-156">. Любой журнал, который может содержать конфиденциальные данные, должен храниться в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="26aaf-156">Any log that contains potentially sensitive information should be stored in a secure location.</span></span>  
  
-   <span data-ttu-id="26aaf-157">**Не допускайте неправильных сведений**</span><span class="sxs-lookup"><span data-stu-id="26aaf-157">**Avoid misleading information.**</span></span> <span data-ttu-id="26aaf-158">. В общем случае приложение должно проверять все данные, введенные пользователем, перед их использованием.</span><span class="sxs-lookup"><span data-stu-id="26aaf-158">In general, your application should validate all data entered by a user before using that data.</span></span> <span data-ttu-id="26aaf-159">Это относится и к записи данных в журнал приложения.</span><span class="sxs-lookup"><span data-stu-id="26aaf-159">This includes writing data to the application log.</span></span>  
  
-   <span data-ttu-id="26aaf-160">**Не допускайте отказа в обслуживании**</span><span class="sxs-lookup"><span data-stu-id="26aaf-160">**Avoid denial of service.**</span></span> <span data-ttu-id="26aaf-161">. Если приложение записывает в журнал слишком много сведений, это может привести к переполнению журнала или усложнить поиск важной информации.</span><span class="sxs-lookup"><span data-stu-id="26aaf-161">If your application writes too much information to the log, it could fill the log or make finding important information difficult.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26aaf-162">См. также</span><span class="sxs-lookup"><span data-stu-id="26aaf-162">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [<span data-ttu-id="26aaf-163">Запись сведений в журнал из приложения</span><span class="sxs-lookup"><span data-stu-id="26aaf-163">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)
