---
title: Практическое руководство. Настройка трассировки сети
ms.date: 03/30/2017
helpviewer_keywords:
- formatting [.NET Framework], network tracing
- network tracing, configuring
- level attribute
- app.config files, network tracing
- configuration files [.NET Framework], network tracing
- protocol-level trace output
- application configuration files, network tracing
- sockets, trace output
ms.assetid: 5ef9fe4b-8d3d-490e-9259-1d014b2181af
ms.openlocfilehash: 06132509860b16d1e22cfdf7e3226c968d16b7cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73040646"
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="6abe6-102">Практическое руководство. Настройка трассировки сети</span><span class="sxs-lookup"><span data-stu-id="6abe6-102">How to: Configure network tracing</span></span>

<span data-ttu-id="6abe6-103">Файл конфигурации приложения или компьютера содержит параметры, которые определяют формат и содержимое данных трассировки сети.</span><span class="sxs-lookup"><span data-stu-id="6abe6-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="6abe6-104">Перед выполнением этой процедуры убедитесь, что трассировка включена.</span><span class="sxs-lookup"><span data-stu-id="6abe6-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="6abe6-105">Дополнительные сведения см. в разделе [Включение трассировки сети](enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="6abe6-105">For more information, see [Enable network tracing](enabling-network-tracing.md).</span></span>

<span data-ttu-id="6abe6-106">Файл конфигурации компьютера *machine.config* хранится в папке *%windir%\Microsoft.NET\Framework*.</span><span class="sxs-lookup"><span data-stu-id="6abe6-106">The computer configuration file, *machine.config*, is stored in the *%windir%\Microsoft.NET\Framework* folder.</span></span> <span data-ttu-id="6abe6-107">В папках внутри *%windir%\Microsoft.NET\Framework* находится отдельный файл *machine.config* для каждой версии .NET Framework, установленной на компьютере:</span><span class="sxs-lookup"><span data-stu-id="6abe6-107">There is a separate *machine.config* file in the folders under *%windir%\Microsoft.NET\Framework* for each version of the .NET Framework installed on the computer, for example:</span></span>

- <span data-ttu-id="6abe6-108">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="6abe6-108">*C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\Config\machine.config*</span></span>
- <span data-ttu-id="6abe6-109">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span><span class="sxs-lookup"><span data-stu-id="6abe6-109">*C:\WINDOWS\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config*</span></span>

<span data-ttu-id="6abe6-110">Эти параметры могут также задаваться в файле конфигурации приложения, который имеет более высокий приоритет, чем в файл конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="6abe6-110">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>

## <a name="configure-network-tracing"></a><span data-ttu-id="6abe6-111">Настройка трассировки сети</span><span class="sxs-lookup"><span data-stu-id="6abe6-111">Configure network tracing</span></span>

<span data-ttu-id="6abe6-112">Чтобы настроить трассировку сети, добавьте следующие строки в соответствующий файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6abe6-112">To configure network tracing, add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="6abe6-113">Значения этих параметров описаны в приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="6abe6-113">The values and options for these settings are described in the tables below.</span></span>

```xml
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Net" tracemode="includehex" maxdatasize="1024">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
      <source name="System.Net.Cache">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
      <source name="System.Net.Http">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
      <source name="System.Net.Sockets">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
      <source name="System.Net.WebSockets">
        <listeners>
          <add name="System.Net"/>
        </listeners>
      </source>
   </sources>
    <switches>
      <add name="System.Net" value="Verbose"/>
      <add name="System.Net.Cache" value="Verbose"/>
      <add name="System.Net.Http" value="Verbose"/>
      <add name="System.Net.Sockets" value="Verbose"/>
      <add name="System.Net.WebSockets" value="Verbose"/>
    </switches>
    <sharedListeners>
      <add name="System.Net"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="network.log"
        traceOutputOptions="ProcessId, DateTime"
      />
    </sharedListeners>
    <trace autoflush="true"/>
  </system.diagnostics>
</configuration>
```

### <a name="trace-output-from-methods"></a><span data-ttu-id="6abe6-114">Выходные данные трассировки из методов</span><span class="sxs-lookup"><span data-stu-id="6abe6-114">Trace output from methods</span></span>

<span data-ttu-id="6abe6-115">При добавлении имени в блок `<switches>` результаты трассировки будут содержать сведения из определенных методов, связанных с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="6abe6-115">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="6abe6-116">Результат описан в следующей таблице:</span><span class="sxs-lookup"><span data-stu-id="6abe6-116">The following table describes the output:</span></span>

|<span data-ttu-id="6abe6-117">name</span><span class="sxs-lookup"><span data-stu-id="6abe6-117">Name</span></span>|<span data-ttu-id="6abe6-118">Источник результата</span><span class="sxs-lookup"><span data-stu-id="6abe6-118">Output from</span></span>|
|----------|-----------------|
|`System.Net.Sockets`|<span data-ttu-id="6abe6-119">Некоторые открытые методы классов <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> и <xref:System.Net.Dns>.</span><span class="sxs-lookup"><span data-stu-id="6abe6-119">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes.</span></span>|
|`System.Net`|<span data-ttu-id="6abe6-120">Некоторые открытые методы классов <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse>, а также отладочные данные SSL (недопустимые сертификаты, отсутствующие издатели и ошибки сертификатов клиентов).</span><span class="sxs-lookup"><span data-stu-id="6abe6-120">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors).</span></span>|
|`System.Net.HttpListener`|<span data-ttu-id="6abe6-121">Некоторые открытые методы классов <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> и <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="6abe6-121">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|
|`System.Net.Cache`|<span data-ttu-id="6abe6-122">Некоторые открытые и закрытые методы в `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="6abe6-122">Some private and internal methods in `System.Net.Cache`.</span></span>|
|`System.Net.Http`|<span data-ttu-id="6abe6-123">Некоторые открытые методы классов <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> и <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="6abe6-123">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="6abe6-124">Некоторые открытые методы классов <xref:System.Net.WebSockets.ClientWebSocket> и <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="6abe6-124">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|

### <a name="trace-output-attributes"></a><span data-ttu-id="6abe6-125">Атрибуты выходных данных трассировки</span><span class="sxs-lookup"><span data-stu-id="6abe6-125">Trace output attributes</span></span>

<span data-ttu-id="6abe6-126">Атрибуты, указанные в следующей таблице, задают выходные данные трассировки:</span><span class="sxs-lookup"><span data-stu-id="6abe6-126">The attributes listed in the following table configure trace output:</span></span>

|<span data-ttu-id="6abe6-127">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="6abe6-127">Attribute name</span></span>|<span data-ttu-id="6abe6-128">Значение атрибута</span><span class="sxs-lookup"><span data-stu-id="6abe6-128">Attribute value</span></span>|
|--------------------|---------------------|
|`value`|<span data-ttu-id="6abe6-129">Обязательный атрибут элемента <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6abe6-129">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="6abe6-130">Задает уровень детализации результатов.</span><span class="sxs-lookup"><span data-stu-id="6abe6-130">Sets the verbosity of the output.</span></span> <span data-ttu-id="6abe6-131">Допустимые значения: `Critical`, `Error`, `Verbose`, `Warning` и `Information`.</span><span class="sxs-lookup"><span data-stu-id="6abe6-131">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /><span data-ttu-id="6abe6-132">Этот атрибут следует задавать в элементе **add** элемента **switches**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-132">This attribute must be set on the **add** element of the **switches** element.</span></span> <span data-ttu-id="6abe6-133">Исключение возникает, если этот атрибут задан для элемента **source**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-133">An exception is thrown if this attribute is set on the **source** element.</span></span><br/><br/><span data-ttu-id="6abe6-134">Пример: `<add name="System.Net" value="Verbose"/>`</span><span class="sxs-lookup"><span data-stu-id="6abe6-134">Example: `<add name="System.Net" value="Verbose"/>`</span></span>|
|`maxdatasize`|<span data-ttu-id="6abe6-135">Необязательный атрибут элемента <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="6abe6-135">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="6abe6-136">Задает максимальное число байтов сетевых данных, включенных в трассировку каждой линии.</span><span class="sxs-lookup"><span data-stu-id="6abe6-136">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="6abe6-137">Значение по умолчанию — 1024.</span><span class="sxs-lookup"><span data-stu-id="6abe6-137">The default value is 1024.</span></span><br /><br /><span data-ttu-id="6abe6-138">Этот атрибут следует задавать в элементе **source**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-138">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="6abe6-139">Исключение возникает, если этот атрибут задан для элемента в элементе **switches**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-139">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="6abe6-140">Пример: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="6abe6-140">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|
|`tracemode`|<span data-ttu-id="6abe6-141">Необязательный атрибут элемента <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6abe6-141">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="6abe6-142">Задается `includehex`, чтобы трассировка протоколов отображалась в шестнадцатеричном или текстовом формате.</span><span class="sxs-lookup"><span data-stu-id="6abe6-142">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="6abe6-143">Установите значение `protocolonly`, чтобы отображался только текст.</span><span class="sxs-lookup"><span data-stu-id="6abe6-143">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="6abe6-144">Значение по умолчанию — `includehex`.</span><span class="sxs-lookup"><span data-stu-id="6abe6-144">The default value is `includehex`.</span></span><br /><br /><span data-ttu-id="6abe6-145">Этот атрибут следует задавать в элементе **source**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-145">This attribute must be set on the **source** element.</span></span> <span data-ttu-id="6abe6-146">Исключение возникает, если этот атрибут задан для элемента в элементе **switches**.</span><span class="sxs-lookup"><span data-stu-id="6abe6-146">An exception is thrown if this attribute is set on an element under the **switches** element.</span></span><br/><br/><span data-ttu-id="6abe6-147">Пример: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span><span class="sxs-lookup"><span data-stu-id="6abe6-147">Example: `<source name="System.Net" tracemode="includehex" maxdatasize="1024">`</span></span>|

## <a name="see-also"></a><span data-ttu-id="6abe6-148">См. также</span><span class="sxs-lookup"><span data-stu-id="6abe6-148">See also</span></span>

- [<span data-ttu-id="6abe6-149">Интерпретация трассировки сети</span><span class="sxs-lookup"><span data-stu-id="6abe6-149">Interpreting Network Tracing</span></span>](interpreting-network-tracing.md)
- [<span data-ttu-id="6abe6-150">Трассировка сети в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6abe6-150">Network Tracing in the .NET Framework</span></span>](network-tracing.md)
- [<span data-ttu-id="6abe6-151">Включение трассировки сети</span><span class="sxs-lookup"><span data-stu-id="6abe6-151">Enabling Network Tracing</span></span>](enabling-network-tracing.md)
- [<span data-ttu-id="6abe6-152">Трассировка и инструментирование приложений</span><span class="sxs-lookup"><span data-stu-id="6abe6-152">Tracing and Instrumenting Applications</span></span>](../debug-trace-profile/tracing-and-instrumenting-applications.md)
