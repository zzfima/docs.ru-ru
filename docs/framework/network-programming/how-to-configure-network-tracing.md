---
title: "Практическое руководство. Настройка трассировки сети"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "23"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b58887dc2614ab31a422eb74ce8d0805cf8153bf
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-configure-network-tracing"></a><span data-ttu-id="db8a9-102">Практическое руководство. Настройка трассировки сети</span><span class="sxs-lookup"><span data-stu-id="db8a9-102">How to: Configure Network Tracing</span></span>
<span data-ttu-id="db8a9-103">Файл конфигурации приложения или компьютера содержит параметры, которые определяют формат и содержимое данных трассировки сети.</span><span class="sxs-lookup"><span data-stu-id="db8a9-103">The application or computer configuration file holds the settings that determine the format and content of network traces.</span></span> <span data-ttu-id="db8a9-104">Перед выполнением этой процедуры убедитесь, что трассировка включена.</span><span class="sxs-lookup"><span data-stu-id="db8a9-104">Before performing this procedure, be sure tracing is enabled.</span></span> <span data-ttu-id="db8a9-105">Сведения о том, как включить трассировку сети, см. в разделе [Включение трассировки сети](../../../docs/framework/network-programming/enabling-network-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="db8a9-105">For information about enabling tracing, see [Enabling Network Tracing](../../../docs/framework/network-programming/enabling-network-tracing.md).</span></span>  
  
 <span data-ttu-id="db8a9-106">Файл конфигурации компьютера (machine.config) хранится в папке %Windir%\Microsoft.NET\Framework в каталоге, в который установлена ОС Windows.</span><span class="sxs-lookup"><span data-stu-id="db8a9-106">The computer configuration file, machine.config, is stored in the %Windir%\Microsoft.NET\Framework folder in the directory where Windows was installed.</span></span> <span data-ttu-id="db8a9-107">В папках %Windir%\Microsoft.NET\Framework для каждой версии платформы .NET Framework, установленной на компьютере (например, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config или C:\Windows\ имеется отдельный файл machine.config Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span><span class="sxs-lookup"><span data-stu-id="db8a9-107">There is a separate machine.config file in the folders under %Windir%\Microsoft.NET\Framework for each version of the .NET Framework installed on the computer (for example, C:\WINDOWS\Microsoft.NET\Framework\v2.0.50727\machine.config or C:\Windows\Microsoft.NET\Framework64\v4.0.30319\Config\machine.config.).</span></span>  
  
 <span data-ttu-id="db8a9-108">Эти параметры могут также задаваться в файле конфигурации приложения, который имеет более высокий приоритет, чем в файл конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="db8a9-108">These settings can also be made in the configuration file for the application, which has precedence over the computer configuration file.</span></span>  
  
### <a name="to-configure-network-tracing"></a><span data-ttu-id="db8a9-109">Настройка трассировки сети</span><span class="sxs-lookup"><span data-stu-id="db8a9-109">To configure network tracing</span></span>  
  
-   <span data-ttu-id="db8a9-110">Добавьте следующие строки в соответствующий файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="db8a9-110">Add the following lines to the appropriate configuration file.</span></span> <span data-ttu-id="db8a9-111">Значения этих параметров описаны в приведенных ниже таблицах.</span><span class="sxs-lookup"><span data-stu-id="db8a9-111">The values and options for these settings are described in the tables below.</span></span>  
  
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
          />  
        </sharedListeners>  
        <trace autoflush="true"/>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
 <span data-ttu-id="db8a9-112">При добавлении имени в блок `<switches>` результаты трассировки будут содержать сведения из определенных методов, связанных с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="db8a9-112">When you add a name to the `<switches>` block, the trace output includes information from some methods related to the name.</span></span> <span data-ttu-id="db8a9-113">Результат описан в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="db8a9-113">The following table describes the output.</span></span>  
  
|<span data-ttu-id="db8a9-114">name</span><span class="sxs-lookup"><span data-stu-id="db8a9-114">Name</span></span>|<span data-ttu-id="db8a9-115">Источник результата</span><span class="sxs-lookup"><span data-stu-id="db8a9-115">Output from</span></span>|  
|----------|-----------------|  
|`System.Net.Sockets`|<span data-ttu-id="db8a9-116">Некоторые открытые методы классов <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient> и <xref:System.Net.Dns></span><span class="sxs-lookup"><span data-stu-id="db8a9-116">Some public methods of the <xref:System.Net.Sockets.Socket>, <xref:System.Net.Sockets.TcpListener>, <xref:System.Net.Sockets.TcpClient>, and <xref:System.Net.Dns> classes</span></span>|  
|`System.Net`|<span data-ttu-id="db8a9-117">Некоторые открытые методы классов <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest> и <xref:System.Net.FtpWebResponse>, а также отладочные данные SSL (недопустимые сертификаты, отсутствующие эмитенты и ошибки сертификатов клиентов).</span><span class="sxs-lookup"><span data-stu-id="db8a9-117">Some public methods of the <xref:System.Net.HttpWebRequest>, <xref:System.Net.HttpWebResponse>, <xref:System.Net.FtpWebRequest>, and <xref:System.Net.FtpWebResponse> classes, and SSL debug information (invalid certificates, missing issuers list, and client certificate errors.)</span></span>|  
|`System.Net.HttpListener`|<span data-ttu-id="db8a9-118">Некоторые открытые методы классов <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest> и <xref:System.Net.HttpListenerResponse>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-118">Some public methods of the <xref:System.Net.HttpListener>, <xref:System.Net.HttpListenerRequest>, and <xref:System.Net.HttpListenerResponse> classes.</span></span>|  
|`System.Net.Cache`|<span data-ttu-id="db8a9-119">Некоторые открытые и закрытые методы в `System.Net.Cache`.</span><span class="sxs-lookup"><span data-stu-id="db8a9-119">Some private and internal methods in `System.Net.Cache`.</span></span>|  
|`System.Net.Http`|<span data-ttu-id="db8a9-120">Некоторые открытые методы классов <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>, <xref:System.Net.Http.MessageProcessingHandler> и <xref:System.Net.Http.WebRequestHandler>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-120">Some public methods of the  <xref:System.Net.Http.HttpClient>,  <xref:System.Net.Http.DelegatingHandler>,  <xref:System.Net.Http.HttpClientHandler>, <xref:System.Net.Http.HttpMessageHandler>,  <xref:System.Net.Http.MessageProcessingHandler>, and  <xref:System.Net.Http.WebRequestHandler> classes.</span></span>|  
|`System.Net.WebSockets.WebSocket`|<span data-ttu-id="db8a9-121">Некоторые открытые методы классов <xref:System.Net.WebSockets.ClientWebSocket> и <xref:System.Net.WebSockets.WebSocket>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-121">Some public methods of the <xref:System.Net.WebSockets.ClientWebSocket> and <xref:System.Net.WebSockets.WebSocket> classes.</span></span>|  
  
 <span data-ttu-id="db8a9-122">Атрибуты, указанные в следующей таблице, задают выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="db8a9-122">The attributes listed in the following table configure trace output.</span></span>  
  
|<span data-ttu-id="db8a9-123">Имя атрибута</span><span class="sxs-lookup"><span data-stu-id="db8a9-123">Attribute name</span></span>|<span data-ttu-id="db8a9-124">Значение атрибута</span><span class="sxs-lookup"><span data-stu-id="db8a9-124">Attribute value</span></span>|  
|--------------------|---------------------|  
|`Value`|<span data-ttu-id="db8a9-125">Обязательный атрибут элемента <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-125">Required <xref:System.String> attribute.</span></span> <span data-ttu-id="db8a9-126">Задает уровень детализации результатов.</span><span class="sxs-lookup"><span data-stu-id="db8a9-126">Sets the verbosity of the output.</span></span> <span data-ttu-id="db8a9-127">Допустимые значения: `Critical`, `Error`, `Verbose`, `Warning` и `Information`.</span><span class="sxs-lookup"><span data-stu-id="db8a9-127">Legitimate values are `Critical`, `Error`, `Verbose`, `Warning`, and `Information`.</span></span><br /><br /> <span data-ttu-id="db8a9-128">Этот атрибут следует установить в элементе \<add name> элемента \<switches>, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="db8a9-128">This attribute must be set on the \<add name> element of the \<switches> element as shown in the example.</span></span> <span data-ttu-id="db8a9-129">Исключение возникает, если этот атрибут задан для элемента \<source>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-129">An exception is thrown if this attribute is set on the \<source> element.</span></span>|  
|`maxdatasize`|<span data-ttu-id="db8a9-130">Необязательный атрибут элемента <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-130">Optional <xref:System.Int32> attribute.</span></span> <span data-ttu-id="db8a9-131">Задает максимальное число байтов сетевых данных, включенных в трассировку каждой линии.</span><span class="sxs-lookup"><span data-stu-id="db8a9-131">Sets the maximum number of bytes of network data included in each line trace.</span></span> <span data-ttu-id="db8a9-132">Значение по умолчанию — 1024.</span><span class="sxs-lookup"><span data-stu-id="db8a9-132">The default value is 1024.</span></span><br /><br /> <span data-ttu-id="db8a9-133">Этот атрибут следует задавать в элементе \<source>, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="db8a9-133">This attribute must be set on the \<source> element as shown in the example.</span></span> <span data-ttu-id="db8a9-134">Исключение возникает, если этот атрибут задан для элемента в элементе \<switches>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-134">An exception is thrown if this attribute is set on an element under the \<switches> element.</span></span>|  
|`Tracemode`|<span data-ttu-id="db8a9-135">Необязательный атрибут элемента <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-135">Optional <xref:System.String> attribute.</span></span> <span data-ttu-id="db8a9-136">Задается `includehex`, чтобы трассировка протоколов отображалась в шестнадцатеричном или текстовом формате.</span><span class="sxs-lookup"><span data-stu-id="db8a9-136">Set to `includehex` to show protocol traces in hexadecimal and text format.</span></span> <span data-ttu-id="db8a9-137">Установите значение `protocolonly`, чтобы отображался только текст.</span><span class="sxs-lookup"><span data-stu-id="db8a9-137">Set to `protocolonly` to show only text.</span></span> <span data-ttu-id="db8a9-138">Значение по умолчанию — `includehex`.</span><span class="sxs-lookup"><span data-stu-id="db8a9-138">The default value is `includehex`.</span></span><br /><br /> <span data-ttu-id="db8a9-139">Этот атрибут следует задавать в элементе \<switches>, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="db8a9-139">This attribute must be set on the \<switches> element as shown in the example.</span></span> <span data-ttu-id="db8a9-140">Исключение возникает, если этот атрибут задан для элемента в элементе \<source>.</span><span class="sxs-lookup"><span data-stu-id="db8a9-140">An exception is thrown if this attribute is set on an element under the \<source> element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db8a9-141">См. также</span><span class="sxs-lookup"><span data-stu-id="db8a9-141">See Also</span></span>  
 [<span data-ttu-id="db8a9-142">Интерпретация трассировки сети</span><span class="sxs-lookup"><span data-stu-id="db8a9-142">Interpreting Network Tracing</span></span>](../../../docs/framework/network-programming/interpreting-network-tracing.md)  
 [<span data-ttu-id="db8a9-143">Трассировка сети в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="db8a9-143">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)  
 [<span data-ttu-id="db8a9-144">Включение трассировки сети</span><span class="sxs-lookup"><span data-stu-id="db8a9-144">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="db8a9-145">Введение. Подготовка к инструментированию и трассировка</span><span class="sxs-lookup"><span data-stu-id="db8a9-145">Introduction to Instrumentation and Tracing</span></span>](http://msdn.microsoft.com/library/e924e57c-33cf-4b0e-9e7f-a45d13e38f2c)
