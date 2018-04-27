---
title: Отслеживание использования с помощью текстового файла
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 32aab8ae875158fed62c70cbc2d7506ba6c8d3c5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="tracking-using-a-text-file"></a>Отслеживание использования с помощью текстового файла
В этом примере показано, как расширить отслеживание в Windows Workflow Foundation (WF) путем создания настраиваемого участника отслеживания. Участниками отслеживания являются классы платформы .NET Framework, которые получают записи отслеживания от среды выполнения при их передаче. Можно создать участника отслеживания для транспортировки событий отслеживания в место назначения, требуемое для сценария. Например, участник отслеживания событий для Windows (ETW) предоставляется как часть [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Участник отслеживания в этом образце записывает записи в текстовый файл в формате XML.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 Для оптимизации применимости и надежности участника отслеживания должны быть выполнены некоторые шаги для правильного подключения участника отслеживания в среду выполнения. В следующей таблице описываются классы, используемые в образце для создания участника отслеживания, который соответствует рекомендациям.  
  
|Класс|Описание|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|Элемент <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> используется для определения раздела конфигурации, используемого для настройки участника отслеживания текстового файла. Это позволяет пользователям указывать место назначения файла журнала с помощью обычных файлов конфигурации платформы .NET Framework.|  
|`TextFileTrackingBehavior`|Разные виды поведения в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяют пользователям внедрять расширения в среду выполнения. Это поведение добавляет участника отслеживания к службе при ее запуске.|  
|`TextFileTrackingParticipant`|Участник отслеживания, который получает участников отслеживания во время выполнения и сохраняет их в файле журнала как XML.|  
  
## <a name="behavior-extension-elements-configuration"></a>Конфигурация элементов расширения поведения  
 Для использования элемента расширения поведения, описанного ранее с помощью файлов конфигурации .NET Framework, требуется выполнить еще один шаг. Если должно использоваться расширение, в файлы конфигурации необходимо внести следующую конфигурацию.  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  См. файл Web.config в образце полного примера использования конфигурации элементов расширения поведения.  
  
## <a name="custom-tracking-records"></a>Пользовательские записи отслеживания  
 Файл GetStockPrices.cs демонстрирует способ создания пользовательских записей отслеживания в <xref:System.Activities.CodeActivity>. При выполнении образца найдите эту запись.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения WFStockPriceApplication.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
     Откроется окно браузера со списком каталогов для приложения.  
  
4.  Щелкните файл StockPriceService.xamlx в браузере.  
  
5.  В браузере отображается **StockPriceService** страницы, содержащей адрес wsdl локальной службы. Скопируйте этот адрес.  
  
     Примером адреса wsdl локальной службы является http://localhost:53797/StockPriceService.xamlx?wsdl.  
  
6.  В [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] перейдите в папку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (по умолчанию папкой установки является папка %SystemDrive%\Program Files\Microsoft Visual Studio 10.0). Затем перейдите в подпапку Common7\IDE\.  
  
7.  Дважды щелкните файл, чтобы запустить тестовый клиент WCF.  
  
8.  В тестовом клиенте WCF выберите **добавить службу...** из **файл** меню.  
  
9. Вставьте в текстовое поле только что скопированный URL-адрес.  
  
10. Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.  
  
11. Проверьте службу с помощью тестового клиента WCF.  
  
    1.  В тестовом клиенте WCF дважды щелкните **GetStockPrice()** под **IStockPriceService** узла.  
  
         **GetStockPrice()** метод отображается в правой области с одним параметром.  
  
    2.  Введите Contoso в качестве значения параметра.  
  
    3.  Нажмите кнопку **вызова**.  
  
12. Просмотрите отслеживаемые события в файле журнала, расположенном в каталоге данных приложения: %APPDATA%\trackingRecords.log.  
  
    > [!NOTE]
    >  % APPDATA % является переменной среды, которая разрешает %SystemDrive%\Users\\< имя_пользователя\>\AppData\Roaming в [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], или Windows Server 2008.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a>См. также  
 [Примеры мониторинга AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
