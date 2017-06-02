---
title: "Отслеживание рабочих процессов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 18737989-0502-4367-b5f6-617ebfb77c96
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Отслеживание рабочих процессов
Трассировка рабочего процесса позволяет получать сведения диагностики при помощи прослушивателей трассировки .NET Framework.Трассировку можно включить при обнаружении проблемы в работе приложения, а затем снова отключить после разрешения проблемы.Существует два способа включения трассировки отладки для рабочих процессов.Можно настроить отслеживание в средстве просмотра трассировки событий либо использовать <xref:System.Diagnostics> для отправки событий трассировки в файл.  
  
## Включение трассировки отладки в ETW  
 Для включения трассировки при помощи ETW включите канал отладки в средстве просмотра событий.  
  
1.  Перейдите в узел аналитики и журналов отладки в средстве просмотра событий.  
  
2.  В представлении дерева в средстве просмотра событий перейдите на вкладку **Средств просмотра событий\-\>Журналы приложений и служб\-\>Microsoft\-\>Windows\-\>Сервер приложений\-приложения**.Правой кнопкой мыши щелкните **Сервер приложений\-приложения** и выберите пункт **Просмотр\-\>Показать аналитику и журналы отладки**.Щелкните правой кнопкой мыши пункт **Отладка** и выберите **Включить журнал**.  
  
3.  Когда рабочий процесс запускает отладку и трассы событий выдаются в канал отладки ETW, их можно просмотреть в средстве просмотра событий.Перейдите на вкладку **Средство просмотра событий\-\>Журналы приложений и служб\-\>Microsoft\-\>Windows\-\>Сервер приложений\-приложения**.Щелкните правой кнопкой мыши пункт **Отладка** и выберите **Обновить**.  
  
4.  Размер буфера аналитической трассировки по умолчанию составляет всего 4 килобайта \(КБ\). Рекомендуется увеличить этот размер до 32 КБ.Для этого выполните следующие действия.  
  
    1.  Выполните следующую команду в текущем каталоге платформы \(например, C:\\Windows\\Microsoft.NET\\Framework\\v4.0.21203\):`wevtutil um Microsoft.Windows.ApplicationServer.Applications.man`  
  
    2.  Измените значение \<bufferSize\> в файле Windows.ApplicationServer.Applications.man на значение 32.  
  
        ```  
        <channel name="Microsoft-Windows-Application Server-Applications/Analytic" chid="ANALYTIC_CHANNEL" symbol="ANALYTIC_CHANNEL" type="Analytic" enabled="false" isolation="Application" message="$(string.MICROSOFT_WINDOWS_APPLICATIONSERVER_APPLICATIONS.channel.ANALYTIC_CHANNEL.message)" >  
                    <publishing>  
                      <bufferSize>32</bufferSize>  
                    </publishing>  
                  </channel>  
  
        ```  
  
    3.  Выполните следующую команду в текущем каталоге платформы \(например, C:\\Windows\\Microsoft.NET\\Framework\\v4.0.21203\):`wevtutil im Microsoft.Windows.ApplicationServer.Applications.man`  
  
> [!NOTE]
>  Если пользователь использует клиентский профиль .NET Framework 4, следует сначала зарегистрировать манифест трассировки событий Windows, выполнив в папке .NET Framework 4 следующую команду: `ServiceModelReg.exe –i –c:etw`  
  
## Включение трассировки отладки при помощи System.Diagnostics  
 Эти прослушиватели можно настроить в файле App.config приложения рабочего процесса либо в файле Web.config для службы рабочего процесса.В этом примере будет настроен параметр [TextWriterTraceListener](http://go.microsoft.com/fwlink/?LinkId=165424) для сохранения информации трассировки в файле MyTraceLog.txt в текущем каталоге.  
  
```  
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
  
## См. также  
 [Наблюдение за фабрикой приложений сервера Windows](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Наблюдение за приложениями с помощью фабрики приложения](http://go.microsoft.com/fwlink/?LinkId=201275)