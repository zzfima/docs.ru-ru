---
title: "Пошаговое руководство. Определение места записи информации для My.Application.Log (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "объект My.Log, расположение выходных данных"
  - "выходные данные, расположение журнала приложения"
  - "объект My.Application.Log, расположение выходных данных"
  - "журналы событий, определение расположения выходных данных"
  - "журналы событий приложений, расположение выходных данных"
  - "приложения [Visual Basic], расположение выходных данных"
ms.assetid: 5b70143a-7741-45f2-ae1d-03324a3a4189
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Пошаговое руководство. Определение места записи информации для My.Application.Log (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Объект `My.Application.Log` может записывать информацию в несколько прослушивателей журналов. Прослушиватели журнала настраиваются в файле конфигурации компьютера и могут переопределяться в файле конфигурации приложения. В этом разделе описаны параметры по умолчанию и способ определения параметров для приложения.  
  
 Дополнительные сведения о расположении выходных данных по умолчанию см. в разделе [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
### Определение прослушивателей для объекта My.Application.Log  
  
1.  Найдите файл конфигурации сборки. Во время разработки сборки доступ к файлу app.config в [!INCLUDE[vsprvs](../../../../csharp/includes/vsprvs_md.md)] можно получить в **обозревателе решений**. В противном случае имя файла конфигурации — это имя сборки с расширением .config, а расположен он в том же каталоге, что и сборка.  
  
    > [!NOTE]
    >  Не каждая сборка имеет файл конфигурации.  
  
     Файл конфигурации является XML\-файлом.  
  
2.  Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name`, равным DefaultSource, в разделе `<sources>`. Раздел `<sources>` находится в разделе `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
     Если эти разделы не существуют, то настройка прослушивателей журнала `My.Application.Log` может быть задана в файле конфигурации компьютера. Далее описано, как выяснить, что определяется в файле конфигурации компьютера.  
  
    1.  Найдите файл machine.config компьютера. Как правило, он находится в каталоге *SystemRoot\\Microsoft.NET\\Framework\\frameworkVersion\\CONFIG*, где `SystemRoot` — каталог операционной системы, а `frameworkVersion` — версия [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
         Параметры в файле machine.config могут быть переопределены файлом конфигурации приложения.  
  
         Если необязательные элементы, перечисленные ниже, отсутствуют, их можно создать.  
  
    2.  Найдите раздел `<listeners>` в разделе `<source>` с атрибутом `name`, равным DefaultSource, в разделе `<sources>` раздела `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
         Если эти разделы не существуют, то в объекте `My.Application.Log` имеются только прослушиватели журнала по умолчанию.  
  
3.  Найдите элементы \<`add>` в разделе \<`listeners>`.  
  
     Эти элементы добавляют именованные прослушиватели журнала в источник `My.Application.Log`.  
  
4.  Найдите элементы `<add>` с именами прослушивателей журнала в разделе `<sharedListeners>` раздела `<system.diagnostics>` в разделе `<configuration>` верхнего уровня.  
  
5.  Данные инициализации для многих типов общих прослушивателей включают описание того, куда прослушиватель направляет данные.  
  
    -   Прослушиватель <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener?displayProperty=fullName> записывает данные в журнал файлов, как описано во введении.  
  
    -   Прослушиватель <xref:System.Diagnostics.EventLogTraceListener?displayProperty=fullName> записывает данные в журнал событий компьютера, определяемый параметром `initializeData`. Для просмотра журнала событий можно использовать **обозреватель сервера** или **средство просмотра событий Windows**. Для получения дополнительной информации см. [ETW Events in the .NET Framework](../Topic/ETW%20Events%20in%20the%20.NET%20Framework.md).  
  
    -   Прослушиватели <xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=fullName> и <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=fullName> записывают данные в файл, указанный в параметре `initializeData`.  
  
    -   Прослушиватель <xref:System.Diagnostics.ConsoleTraceListener?displayProperty=fullName> выводит данные в консоль командной строки.  
  
    -   Сведения о том, куда записывают информацию другие типы прослушивателей журналов, приведены в документации по этим типам.  
  
## См. также  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:System.Diagnostics.DefaultTraceListener>   
 <xref:System.Diagnostics.EventLogTraceListener>   
 <xref:System.Diagnostics.DelimitedListTraceListener>   
 <xref:System.Diagnostics.XmlWriterTraceListener>   
 <xref:System.Diagnostics.ConsoleTraceListener>   
 <xref:System.Diagnostics>   
 [Работа с журналами приложения](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Практическое руководство. Запись в журнал сведений об исключениях](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)   
 [Практическое руководство. Запись сообщений в журнал](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [Пошаговое руководство. Изменение места записи информации для My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)   
 [ETW Events in the .NET Framework](../Topic/ETW%20Events%20in%20the%20.NET%20Framework.md)   
 [Устранение неполадок, связанных с прослушивателями журнала](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)