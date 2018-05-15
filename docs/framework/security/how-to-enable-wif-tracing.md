---
title: Практическое руководство. Включение трассировки WIF
ms.date: 03/30/2017
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 459d74f3faf9fab4cba047a87ccff77d193e9026
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-wif-tracing"></a><span data-ttu-id="ccabb-102">Практическое руководство. Включение трассировки WIF</span><span class="sxs-lookup"><span data-stu-id="ccabb-102">How To: Enable WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="ccabb-103">Применение</span><span class="sxs-lookup"><span data-stu-id="ccabb-103">Applies To</span></span>  
  
-   <span data-ttu-id="ccabb-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="ccabb-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="ccabb-105">Веб-формы ASP.NET®</span><span class="sxs-lookup"><span data-stu-id="ccabb-105">ASP.NET® Web Forms</span></span>  
  
## <a name="summary"></a><span data-ttu-id="ccabb-106">Сводка</span><span class="sxs-lookup"><span data-stu-id="ccabb-106">Summary</span></span>  
 <span data-ttu-id="ccabb-107">Это практическое руководство содержит подробные пошаговые инструкции по включению трассировки WIF в приложении ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ccabb-107">This How-To provides detailed step-by-step procedures for enabling WIF tracing in an ASP.NET application.</span></span> <span data-ttu-id="ccabb-108">В нем также приведены инструкции по тестированию приложения, которые позволяют проверить правильную работу прослушивателя трассировки и журнала.</span><span class="sxs-lookup"><span data-stu-id="ccabb-108">It also provides instructions testing the application to verify that the trace listener and log are working correctly.</span></span> <span data-ttu-id="ccabb-109">В этом практическом руководстве нет подробных инструкций по созданию службы токенов безопасности (STS); вместо этого используется служба Development STS, входящая в состав средства Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="ccabb-109">This How-To does not have detailed instructions for creating a Security Token Service (STS), and instead uses the Development STS that comes with the Identity and Access tool.</span></span> <span data-ttu-id="ccabb-110">Служба Development STS не выполняет фактическую аутентификацию и предназначена только для тестирования.</span><span class="sxs-lookup"><span data-stu-id="ccabb-110">The Development STS does not perform real authentication and is intended for testing purposes only.</span></span> <span data-ttu-id="ccabb-111">Для выполнения этого практического руководства необходимо установить средство Identity and Access Tool.</span><span class="sxs-lookup"><span data-stu-id="ccabb-111">You will need to install the Identity and Access tool to complete this How-To.</span></span> <span data-ttu-id="ccabb-112">Его можно скачать на следующей странице: [Средство Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)</span><span class="sxs-lookup"><span data-stu-id="ccabb-112">It can be downloaded from the following location: [Identity and Access Tool](http://go.microsoft.com/fwlink/?LinkID=245849)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ccabb-113">Включение трассировки WIF для пассивных приложений, то есть для приложений, использующих протокол WS-Federation, может привести к тому, что приложение станет уязвимым к атакам типа "отказ в обслуживании" или к раскрытию конфиденциальной информации.</span><span class="sxs-lookup"><span data-stu-id="ccabb-113">Enabling WIF tracing for passive applications, that is, applications that use the WS-Federation protocol, can potentially expose the application to denial of service (DoS) attacks or to information disclosure to a malicious party.</span></span> <span data-ttu-id="ccabb-114">К таким приложениям относятся как пассивные приложения PR (приложения проверяющей стороны), так и пассивные приложения STS.</span><span class="sxs-lookup"><span data-stu-id="ccabb-114">This includes both passive RPs and passive STSes.</span></span> <span data-ttu-id="ccabb-115">По этой причине рекомендуется не включать трассировку WIF для пассивных приложений RP или STS в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="ccabb-115">For this reason, we recommend that you not enable WIF tracing for passive RPs or STSes in a production environment.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="ccabb-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ccabb-116">Contents</span></span>  
  
-   <span data-ttu-id="ccabb-117">Цели</span><span class="sxs-lookup"><span data-stu-id="ccabb-117">Objectives</span></span>  
  
-   <span data-ttu-id="ccabb-118">Обзор</span><span class="sxs-lookup"><span data-stu-id="ccabb-118">Overview</span></span>  
  
-   <span data-ttu-id="ccabb-119">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="ccabb-119">Summary of Steps</span></span>  
  
-   <span data-ttu-id="ccabb-120">Шаг 1. Создание простого приложения веб-форм ASP.NET и включение трассировки</span><span class="sxs-lookup"><span data-stu-id="ccabb-120">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="ccabb-121">Шаг 2. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="ccabb-121">Step 2 – Test Your Solution</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="ccabb-122">Цели</span><span class="sxs-lookup"><span data-stu-id="ccabb-122">Objectives</span></span>  
  
-   <span data-ttu-id="ccabb-123">Создание простого приложения ASP.NET, которое использует WIF и службу Development STS в составе средства Identity and Access Tool</span><span class="sxs-lookup"><span data-stu-id="ccabb-123">Create a simple ASP.NET application that uses WIF and the Development STS from the Identity and Access Tool</span></span>  
  
-   <span data-ttu-id="ccabb-124">Включение трассировки и проверка ее работы</span><span class="sxs-lookup"><span data-stu-id="ccabb-124">Enable tracing and verify that it is working</span></span>  
  
## <a name="overview"></a><span data-ttu-id="ccabb-125">Обзор</span><span class="sxs-lookup"><span data-stu-id="ccabb-125">Overview</span></span>  
 <span data-ttu-id="ccabb-126">Трассировка позволяет отлаживать и решать различные проблемы, связанные с WIF, в том числе с маркерами, файлами cookie, утверждениями, сообщениями протокола и др.</span><span class="sxs-lookup"><span data-stu-id="ccabb-126">Tracing enables you to debug and troubleshoot many types of issues with WIF, including tokens, cookies, claims, protocol messages, and more.</span></span> <span data-ttu-id="ccabb-127">Трассировка WIF похожа на трассировку WCF; например, вы можете выбрать уровень детализации трассировки для отображения всех сообщений или только критических сообщений.</span><span class="sxs-lookup"><span data-stu-id="ccabb-127">WIF tracing is similar to WCF tracing; for example, you can choose the verbosity of traces to display everything from critical messages to all messages.</span></span> <span data-ttu-id="ccabb-128">Трассировка WIF может создаваться в файлах **.xml** или в файлах **.svclog**, которые можно просмотреть с помощью средства просмотра трассировки служб.</span><span class="sxs-lookup"><span data-stu-id="ccabb-128">WIF traces can be generated in **.xml** files or in **.svclog** files that are viewable by using the Service Trace Viewer Tool.</span></span> <span data-ttu-id="ccabb-129">Это средство находится в каталоге **bin** в папке установки пакета Windows SDK на вашем компьютере, например: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-129">This tool is located in the **bin** directory of the Windows SDK install path on your computer, for example: **C:\Program Files\Microsoft SDKs\Windows\v7.1\Bin\SvcTraceViewer.exe**.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="ccabb-130">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="ccabb-130">Summary of Steps</span></span>  
  
-   <span data-ttu-id="ccabb-131">Шаг 1. Создание простого приложения веб-форм ASP.NET и включение трассировки</span><span class="sxs-lookup"><span data-stu-id="ccabb-131">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
  
-   <span data-ttu-id="ccabb-132">Шаг 2. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="ccabb-132">Step 2 – Test Your Solution</span></span>  
  
## <a name="step-1--create-a-simple-aspnet-web-forms-application-and-enable-tracing"></a><span data-ttu-id="ccabb-133">Шаг 1. Создание простого приложения веб-форм ASP.NET и включение трассировки</span><span class="sxs-lookup"><span data-stu-id="ccabb-133">Step 1 – Create a Simple ASP.NET Web Forms Application and Enable Tracing</span></span>  
 <span data-ttu-id="ccabb-134">На этом шаге вы создадите приложение веб-форм ASP.NET и включите трассировку, изменив файл *Web.config*.</span><span class="sxs-lookup"><span data-stu-id="ccabb-134">In this step, you will create a new ASP.NET Web Forms application and modify the *Web.config* file to enable tracing.</span></span>  
  
#### <a name="to-create-a-simple-aspnet-application"></a><span data-ttu-id="ccabb-135">Создание простого приложения ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ccabb-135">To create a simple ASP.NET application</span></span>  
  
1.  <span data-ttu-id="ccabb-136">Запустите Visual Studio и выберите **Файл**, **Создать** и затем **Проект**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-136">Start Visual Studio and click **File**, **New**, and then **Project**.</span></span>  
  
2.  <span data-ttu-id="ccabb-137">В окне **Новый проект** выберите **Приложение веб-форм ASP.NET**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-137">In the **New Project** window, click **ASP.NET Web Forms Application**.</span></span>  
  
3.  <span data-ttu-id="ccabb-138">В поле **Имя** введите `TestApp` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-138">In **Name**, enter `TestApp` and press **OK**.</span></span>  
  
4.  <span data-ttu-id="ccabb-139">В **обозревателе решений** щелкните правой кнопкой мыши проект **TestApp**, а затем выберите **Идентификация и доступ**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-139">Right-click the **TestApp** project under **Solution Explorer**, then select **Identity and Access**.</span></span>  
  
5.  <span data-ttu-id="ccabb-140">Откроется окно **Идентификация и доступ**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-140">The **Identity and Access** window appears.</span></span> <span data-ttu-id="ccabb-141">В поле **Поставщики** выберите **Протестировать приложение с помощью локальной службы Development STS** и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-141">Under **Providers**, select **Test your application with the Local Development STS**, then click **Apply**.</span></span>  
  
6.  <span data-ttu-id="ccabb-142">Создайте папку **logs** в корне диска **C:** (**C:\logs**).</span><span class="sxs-lookup"><span data-stu-id="ccabb-142">Create a new folder in named **logs** in the root of the **C:** drive, like shown: **C:\logs**</span></span>  
  
7.  <span data-ttu-id="ccabb-143">Добавьте следующий элемент **\<system.diagnostics>** в файл конфигурации *Web.config* сразу после закрывающего элемента **\</configSections>**, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="ccabb-143">Add the following **\<system.diagnostics>** element to the *Web.config* configuration file immediately following the closing **\</configSections>** element, like shown:</span></span>  
  
    ```xml  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ccabb-144">Для создания журналов каталог, указанный в атрибуте **initializeData**, должен существовать на диске.</span><span class="sxs-lookup"><span data-stu-id="ccabb-144">The directory location specified in the **initializeData** attribute must exist before logging can begin.</span></span> <span data-ttu-id="ccabb-145">Если этого каталога не существует, журналы не будут созданы.</span><span class="sxs-lookup"><span data-stu-id="ccabb-145">If the location does not exist, no logs will be created.</span></span>  
  
     <span data-ttu-id="ccabb-146">С приведенными выше параметрами будет включен **подробный** уровень трассировки для WIF, а полученный журнал будет сохранен в файле **C:\logs\WIF.xml**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-146">The configuration settings above will enable **Verbose** tracing for WIF and save the resulting log to the **C:logsWIF.xml** file.</span></span>  
  
## <a name="step-2--test-your-solution"></a><span data-ttu-id="ccabb-147">Шаг 2. Тестирование решения</span><span class="sxs-lookup"><span data-stu-id="ccabb-147">Step 2 – Test Your Solution</span></span>  
 <span data-ttu-id="ccabb-148">На этом шаге вы проверите запись журналов в приложении ASP.NET с поддержкой WIF.</span><span class="sxs-lookup"><span data-stu-id="ccabb-148">In this step, you will test your WIF-enabled ASP.NET application to verify that logs are being recorded.</span></span>  
  
#### <a name="to-test-your-wif-enabled-aspnet-application-for-successful-tracing"></a><span data-ttu-id="ccabb-149">Проверка трассировки в приложении ASP.NET с поддержкой WIF</span><span class="sxs-lookup"><span data-stu-id="ccabb-149">To test your WIF-enabled ASP.NET application for successful tracing</span></span>  
  
1.  <span data-ttu-id="ccabb-150">Запустите решение, нажав клавишу **F5**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-150">Run the solution by pressing the **F5** key.</span></span> <span data-ttu-id="ccabb-151">Откроется домашняя страница ASP.NET по умолчанию, и будет выполнен автоматический вход в систему с именем пользователя *Terry*. Это пользователь по умолчанию для службы Development STS.</span><span class="sxs-lookup"><span data-stu-id="ccabb-151">You should be presented with the default ASP.NET Home Page and automatically authenticated with the username *Terry*, which is the default user that is returned by the Development STS.</span></span>  
  
2.  <span data-ttu-id="ccabb-152">Закройте окно браузера и перейдите в папку **C:\logs**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-152">Close the browser window and then navigate to the **C:\logs** folder.</span></span> <span data-ttu-id="ccabb-153">Откройте файл **C:\logs\WIF.xml** в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="ccabb-153">Open the **C:\logs\WIF.xml** file using a text editor.</span></span>  
  
3.  <span data-ttu-id="ccabb-154">Просмотрите файл **WIF.xml** и убедитесь, что в нем есть записи, которые начинаются с элемента **\<E2ETraceEvent>**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-154">Inspect the **WIF.xml** file and verify that it contains entries starting with **\<E2ETraceEvent>**.</span></span> <span data-ttu-id="ccabb-155">Эти записи трассировки будут содержать элементы **\<TraceRecord>** с описаниями действий трассировки, например **Validating SecurityToken**.</span><span class="sxs-lookup"><span data-stu-id="ccabb-155">These traces will contain **\<TraceRecord>** elements with descriptions for the traced activity, such as **Validating SecurityToken**.</span></span>
