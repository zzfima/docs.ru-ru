---
title: Отслеживание рабочих процессов
ms.date: 03/30/2017
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
ms.openlocfilehash: 972520aae7a2af950ed1ba079769861173784148
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837510"
---
# <a name="workflow-tracing"></a>Отслеживание рабочих процессов
Трассировка рабочего процесса позволяет получать сведения диагностики при помощи прослушивателей трассировки .NET Framework. Трассировку можно включить при обнаружении проблемы в работе приложения, а затем снова отключить после разрешения проблемы. Существует два способа включения трассировки отладки для рабочих процессов. Можно настроить отслеживание в средстве просмотра трассировки событий либо использовать <xref:System.Diagnostics> для отправки событий трассировки в файл.  
  
## <a name="enabling-debug-tracing-in-etw"></a>Включение трассировки отладки в ETW  
 Для включения трассировки при помощи ETW включите канал отладки в средстве просмотра событий.  
  
1. Перейдите в узел аналитики и журналов отладки в средстве просмотра событий.  
  
2. В представлении в виде дерева в Просмотр событий перейдите к **Просмотр событий-> журналы приложений и служб — > Microsoft-> Windows-> сервер приложений — приложения**. Щелкните правой кнопкой мыши **сервер приложений — приложения** и выберите **вид-> Показать журналы аналитики и отладки**. Щелкните правой кнопкой мыши **Отладка** и выберите **Включить журнал**.  
  
3. Когда рабочий процесс запускает отладку и трассы событий выдаются в канал отладки ETW, их можно просмотреть в средстве просмотра событий. Перейдите к разделу **Просмотр событий-> журналы приложений и служб-> Microsoft-> Windows-> сервер приложений — приложения**. Щелкните правой кнопкой мыши элемент **Отладка** и выберите команду **Обновить**.  
  
4. Размер буфера аналитической трассировки по умолчанию составляет всего 4 килобайта (КБ). Рекомендуется увеличить этот размер до 32 КБ. Для этого выполните следующие действия.  
  
    1. Выполните следующую команду в текущем каталоге платформы (например, C:\Windows\Microsoft.NET\Framework\v4.0.21203):`wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2. Измените значение параметра \<bufferSize > в файле Windows. ApplicationServer. Applications. Man на 32.  
  
        ```xml  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
        ```  
  
    3. Выполните следующую команду в текущем каталоге платформы (например, C:\Windows\Microsoft.NET\Framework\v4.0.21203):`wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
> Если вы используете клиентский профиль .NET Framework 4, сначала необходимо зарегистрировать манифест ETW, выполнив следующую команду из каталога .NET Framework 4: `ServiceModelReg.exe –i –c:etw`  
  
## <a name="enabling-debug-tracing-using-systemdiagnostics"></a>Включение трассировки отладки при помощи System.Diagnostics  
 Эти прослушиватели можно настроить в файле App.config приложения рабочего процесса либо в файле Web.config для службы рабочего процесса. В этом примере <xref:System.Diagnostics.TextWriterTraceListener> настроен для сохранения данных трассировки в файле файле mytracelog. txt в текущем каталоге.  
  
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
  
## <a name="see-also"></a>См. также:

- [Мониторинг Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677251(v=azure.10))
- [Мониторинг приложений с помощью App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677276(v=azure.10))
