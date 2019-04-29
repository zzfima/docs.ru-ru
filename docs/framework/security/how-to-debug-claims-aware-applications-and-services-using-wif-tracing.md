---
title: 'Как выполнить: Отладка приложений и служб с помощью трассировки WIF'
ms.date: 03/30/2017
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
author: BrucePerlerMS
ms.openlocfilehash: 43fa859aa84189817dffe74ecd72253ab9b82585
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940495"
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a><span data-ttu-id="66098-102">Как выполнить: Отладка приложений и служб с помощью трассировки WIF</span><span class="sxs-lookup"><span data-stu-id="66098-102">How To: Debug Claims-Aware Applications And Services Using WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="66098-103">Применение</span><span class="sxs-lookup"><span data-stu-id="66098-103">Applies To</span></span>  
  
- <span data-ttu-id="66098-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="66098-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
- <span data-ttu-id="66098-105">Программа Service Trace Viewer (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="66098-105">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>  
  
- <span data-ttu-id="66098-106">Устранение неполадок и отладка приложений WIF</span><span class="sxs-lookup"><span data-stu-id="66098-106">Troubleshooting and Debugging WIF Applications</span></span>  
  
## <a name="summary"></a><span data-ttu-id="66098-107">Сводка</span><span class="sxs-lookup"><span data-stu-id="66098-107">Summary</span></span>  
 <span data-ttu-id="66098-108">В этом практическом руководстве описаны действия, необходимые для настройки трассировки WIF, сбора журналов трассировки и анализа журналов трассировки с помощью средства Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="66098-108">This How-To describes required steps for how to configure WIF tracing, collect trace logs, and how to analyze the trace logs using Trace Viewer tool.</span></span> <span data-ttu-id="66098-109">Здесь предоставляется общее сопоставление записей трассировки с действиями, необходимыми для устранения проблем, связанных с WIF.</span><span class="sxs-lookup"><span data-stu-id="66098-109">It provides general mapping for trace entries to actions needed to troubleshoot issues related to WIF.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="66098-110">Описание</span><span class="sxs-lookup"><span data-stu-id="66098-110">Contents</span></span>  
  
- <span data-ttu-id="66098-111">Цели</span><span class="sxs-lookup"><span data-stu-id="66098-111">Objectives</span></span>  
  
- <span data-ttu-id="66098-112">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="66098-112">Summary of Steps</span></span>  
  
- <span data-ttu-id="66098-113">Шаг 1. Настройка трассировки WIF с помощью файла конфигурации Web.config</span><span class="sxs-lookup"><span data-stu-id="66098-113">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
- <span data-ttu-id="66098-114">Шаг 2. Анализ файлов трассировки WIF с помощью средства Trace Viewer</span><span class="sxs-lookup"><span data-stu-id="66098-114">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
- <span data-ttu-id="66098-115">Шаг 3. Определение решений для устранения проблем WIF</span><span class="sxs-lookup"><span data-stu-id="66098-115">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
- <span data-ttu-id="66098-116">Связанные элементы:</span><span class="sxs-lookup"><span data-stu-id="66098-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="66098-117">Цели</span><span class="sxs-lookup"><span data-stu-id="66098-117">Objectives</span></span>  
  
- <span data-ttu-id="66098-118">Настройка трассировки WIF.</span><span class="sxs-lookup"><span data-stu-id="66098-118">Configure WIF tracing.</span></span>  
  
- <span data-ttu-id="66098-119">Просмотр журналов трассировки в средстве Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="66098-119">View trace logs in the Trace Viewer tool.</span></span>  
  
- <span data-ttu-id="66098-120">Определение проблем, связанных с WIF, в журналах трассировки.</span><span class="sxs-lookup"><span data-stu-id="66098-120">Identify WIF related issues in the trace logs.</span></span>  
  
- <span data-ttu-id="66098-121">Применение корректирующих действий для проблем, связанных с WIF, которые обнаружены в журналах трассировки.</span><span class="sxs-lookup"><span data-stu-id="66098-121">Apply corrective actions to WIF related issues found in the trace logs.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="66098-122">Сводка действий</span><span class="sxs-lookup"><span data-stu-id="66098-122">Summary of Steps</span></span>  
  
- <span data-ttu-id="66098-123">Шаг 1. Настройка трассировки WIF с помощью файла конфигурации Web.config</span><span class="sxs-lookup"><span data-stu-id="66098-123">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
- <span data-ttu-id="66098-124">Шаг 2. Анализ файлов трассировки WIF с помощью средства Trace Viewer</span><span class="sxs-lookup"><span data-stu-id="66098-124">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
- <span data-ttu-id="66098-125">Шаг 3. Определение решений для устранения проблем WIF</span><span class="sxs-lookup"><span data-stu-id="66098-125">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="66098-126">Шаг 1. Настройка трассировки WIF с помощью файла конфигурации Web.config</span><span class="sxs-lookup"><span data-stu-id="66098-126">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
 <span data-ttu-id="66098-127">На этом шаге вы будете добавлять изменения в разделы конфигурации файла *Web.config*, которые включают в WIF трассировку событий и сохранение их в журнале трассировки.</span><span class="sxs-lookup"><span data-stu-id="66098-127">In this step, you will add changes to configuration sections in the *Web.config* file that enable WIF to trace its events and store them in a trace log.</span></span>  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="66098-128">Настройка трассировки WIF с помощью файла конфигурации Web.config</span><span class="sxs-lookup"><span data-stu-id="66098-128">To configure WIF tracing using Web.config configuration file</span></span>  
  
1. <span data-ttu-id="66098-129">Откройте корневой файл конфигурации **Web.config** или **App.config** в редакторе Visual Studio, дважды щелкнув его в **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="66098-129">Open the root **Web.config** or **App.config** configuration file in the Visual Studio editor by double clicking on it in **Solution Explorer**.</span></span> <span data-ttu-id="66098-130">Если в решении отсутствует файл конфигурации **Web.config** или **App.config**, добавьте его, щелкнув правой кнопкой мыши решение в **обозревателе решений**, выбрав пункт **Добавить**, а затем **Новый элемент...**</span><span class="sxs-lookup"><span data-stu-id="66098-130">If your solution does not have **Web.config** or **App.config** configuration file, add it by right clicking on the solution in the **Solution Explorer** and clicking **Add**, then clicking **New Item…**.</span></span> <span data-ttu-id="66098-131">В диалоговом окне **создания элемента** выберите в списке **файл конфигурации приложения**, чтобы создать **App.config**, или **файл веб-конфигурации**, чтобы создать **Web.config**, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="66098-131">On the **New Item** dialog, Select **Application Configuration File** for **App.config** or **Web Configuration File** for **Web.config** from the list and click **OK**.</span></span>  
  
2. <span data-ttu-id="66098-132">Добавьте записи конфигурации, аналогичные приведенным ниже, в узле **\<configuration>** в конце файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="66098-132">Add the configuration entries similar to the following to the configuration file inside **\<configuration>** node at the end of the configuration file:</span></span>  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3. <span data-ttu-id="66098-133">Приведенная выше конфигурация предписывает WIF создавать подробные события трассировки и регистрировать их в файле *WIFTrace.e2e*.</span><span class="sxs-lookup"><span data-stu-id="66098-133">The above configuration instructs WIF to generate verbose trace events and log them into *WIFTrace.e2e* file.</span></span> <span data-ttu-id="66098-134">Полный список значений для **switchValue** см. в таблице уровень трассировки в следующем разделе: [Настройка трассировки](../wcf/diagnostics/tracing/configuring-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="66098-134">For a complete list of values for the **switchValue** switch, refer to the Trace Level table found in the following topic: [Configuring Tracing](../wcf/diagnostics/tracing/configuring-tracing.md).</span></span>  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a><span data-ttu-id="66098-135">Шаг 2. Анализ файлов трассировки WIF с помощью средства Trace Viewer</span><span class="sxs-lookup"><span data-stu-id="66098-135">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
 <span data-ttu-id="66098-136">На этом шаге вы будете использовать средство Trace Viewer (SvcTraceViewer.exe) для анализа журналов трассировки WIF.</span><span class="sxs-lookup"><span data-stu-id="66098-136">In this step, you will use the Trace Viewer Tool (SvcTraceViewer.exe) to analyze WIF trace logs.</span></span>  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a><span data-ttu-id="66098-137">Анализ журналов трассировки WIF с помощью средства Trace Viewer (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="66098-137">To analyze WIF trace logs using Trace Viewer tool (SvcTraceViewer.exe)</span></span>  
  
1. <span data-ttu-id="66098-138">Средство Trace Viewer (SvcTraceViewer.exe) поставляется в составе пакета Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="66098-138">Trace Viewer tool (SvcTraceViewer.exe) ships as part of the Windows SDK.</span></span> <span data-ttu-id="66098-139">Если вы еще не установили пакет Windows SDK, его можно загрузить здесь: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span><span class="sxs-lookup"><span data-stu-id="66098-139">If you haven’t already installed the Windows SDK, you can download it here: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span></span>  
  
2. <span data-ttu-id="66098-140">Запустите средство Trace Viewer (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="66098-140">Run the Trace Viewer tool (SvcTraceViewer.exe).</span></span> <span data-ttu-id="66098-141">Обычно оно находится в папке **Bin** по пути установки.</span><span class="sxs-lookup"><span data-stu-id="66098-141">It is typically available in the **Bin** folder of the installation path.</span></span>  
  
3. <span data-ttu-id="66098-142">Откройте файл журнала трассировки WIF, например WIFTrace.e2e, выбрав в меню пункты **Файл** и **Открыть...**</span><span class="sxs-lookup"><span data-stu-id="66098-142">Open the WIF trace log file, for example, WIFTrace.e2e by selecting **File**, **Open…**</span></span> <span data-ttu-id="66098-143">или нажав клавиши **CTRL+O**.</span><span class="sxs-lookup"><span data-stu-id="66098-143">option in the menu or using the **Ctrl+O** shortcut.</span></span> <span data-ttu-id="66098-144">Файл журнала трассировки откроется в средстве Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="66098-144">The trace log file opens in the Trace Viewer tool.</span></span>  
  
4. <span data-ttu-id="66098-145">Просмотрите записи на вкладке **Действия**. Каждая запись должна содержать номер действия, количество зарегистрированных трассировок, длительность действия и метки времени его начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="66098-145">Review entries in the **Activity** tab. Each entry should contain an activity number, the number of traces that were logged, duration of the activity and its start and end timestamps.</span></span>  
  
5. <span data-ttu-id="66098-146">Перейдите на вкладку **Действия**. Вы увидите подробные записи трассировки в главной области средства.</span><span class="sxs-lookup"><span data-stu-id="66098-146">Click on the **Activity** tab. You should see detailed trace entries in the main area of the tool.</span></span> <span data-ttu-id="66098-147">Используйте **уровень** раскрывающегося списка в меню, чтобы отфильтровать конкретный уровень трассировки, например: **Все**, **предупреждение**, **ошибки**, **сведения**и т. д.</span><span class="sxs-lookup"><span data-stu-id="66098-147">Use the **Level** dropdown list on the menu to filter specific level of traces, for example: **All**, **Warning**, **Errors**, **Information**, etc.</span></span>  
  
6. <span data-ttu-id="66098-148">Щелкните конкретные записи трассировки, чтобы просмотреть сведения в нижней области средства.</span><span class="sxs-lookup"><span data-stu-id="66098-148">Click on specific trace entries to review the details in the lower area of the tool.</span></span> <span data-ttu-id="66098-149">Подробные сведения можно просматривать с помощью представления **Форматированный** и **XML**, выбрав соответствующую вкладку.</span><span class="sxs-lookup"><span data-stu-id="66098-149">The details can be viewed using **Formatted** and **XML** view by choosing corresponding tabs.</span></span>  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="66098-150">Шаг 3. Определение решений для устранения проблем WIF</span><span class="sxs-lookup"><span data-stu-id="66098-150">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
 <span data-ttu-id="66098-151">На этом шаге можно определить решения для проблем, связанных с WIF, обнаруженных с помощью журнала трассировки WIF и средства Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="66098-151">In this step, you can identify solutions for WIF-related issues identified by using the WIF trace log and Trace Viewer tool.</span></span> <span data-ttu-id="66098-152">Здесь представляется общее сопоставление исключений, связанных с WIF, с потенциальными решениями или необходимыми действиями для устранения проблем.</span><span class="sxs-lookup"><span data-stu-id="66098-152">It outlines general mapping of WIF related exceptions to potential solutions or required actions to troubleshoot the issue.</span></span>  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="66098-153">Определение решений для устранения проблем WIF</span><span class="sxs-lookup"><span data-stu-id="66098-153">To identify solutions to fix WIF related issues</span></span>  
  
1. <span data-ttu-id="66098-154">Ознакомьтесь со следующей таблицей исключений WIF и необходимых действий для исправления проблем.</span><span class="sxs-lookup"><span data-stu-id="66098-154">Review the following table of WIF exceptions and the required actions to correct the issues.</span></span>  
  
|<span data-ttu-id="66098-155">**Идентификатор ошибки**</span><span class="sxs-lookup"><span data-stu-id="66098-155">**Error ID**</span></span>|<span data-ttu-id="66098-156">**Сообщение об ошибке**</span><span class="sxs-lookup"><span data-stu-id="66098-156">**Error Message**</span></span>|<span data-ttu-id="66098-157">**Действие, необходимое для исправления ошибки**</span><span class="sxs-lookup"><span data-stu-id="66098-157">**Action needed to fix the error**</span></span>|  
|-|-|-|  
|<span data-ttu-id="66098-158">ID4175</span><span class="sxs-lookup"><span data-stu-id="66098-158">ID4175</span></span>|<span data-ttu-id="66098-159">Издатель токена безопасности не был распознан IssuerNameRegistry.</span><span class="sxs-lookup"><span data-stu-id="66098-159">The issuer of the security token was not recognized by the IssuerNameRegistry.</span></span>  <span data-ttu-id="66098-160">Чтобы принимать токены безопасности от этого издателя, настройте IssuerNameRegistry для возврата допустимого имени этого издателя.</span><span class="sxs-lookup"><span data-stu-id="66098-160">To accept security tokens from this issuer, configure the IssuerNameRegistry to return a valid name for this issuer.</span></span>|<span data-ttu-id="66098-161">Это ошибка может быть вызвана копированием отпечатка из оснастки MMC и вставкой его в файл *Web.config*.</span><span class="sxs-lookup"><span data-stu-id="66098-161">This error can be caused by copying a thumbprint from the MMC snap-in and pasting it into the *Web.config* file.</span></span> <span data-ttu-id="66098-162">В частности, при копировании из окна свойств сертификата можно получить лишний непечатаемый символ в текстовой строке.</span><span class="sxs-lookup"><span data-stu-id="66098-162">Specifically, you can get an extra non-printable character in the text string when copying from the certificate properties window.</span></span> <span data-ttu-id="66098-163">Этот лишний символ приводит к сбою отпечатка. Процедуру правильного копирования отпечатка можно найти в [единый вход на основе утверждений-на для Microsoft Azure и веб-](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).</span><span class="sxs-lookup"><span data-stu-id="66098-163">This extra character causes the thumbprint match to fail.The procedure for correctly copying the thumbprint can be found at [Claims-Based Single Sign-On for the Web and Microsoft Azure](https://docs.microsoft.com/previous-versions/msp-n-p/ff359102%28v=pandp.10%29).</span></span>|  
  
## <a name="related-items"></a><span data-ttu-id="66098-164">Связанные элементы:</span><span class="sxs-lookup"><span data-stu-id="66098-164">Related Items</span></span>  
  
- [<span data-ttu-id="66098-165">Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="66098-165">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
