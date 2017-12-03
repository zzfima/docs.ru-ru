---
title: "Образец интеграции с SystemWebRouting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1c94802-95c4-49e4-b1e2-ee9dd126ff93
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c38c7af4988e6e47ee307f5cd7a8b6733b043a7c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="systemwebrouting-integration-sample"></a>Образец интеграции с SystemWebRouting
Этот образец показывает интеграцию уровня размещения с классами в пространстве имен <xref:System.Web.Routing>. Классы в пространстве имен <xref:System.Web.Routing> позволяют приложению использовать URL-адреса, которые не соответствуют непосредственно физическому ресурсу. С помощью веб-маршрутизации разработчик может создавать виртуальные адреса протокола HTTP, которые затем сопоставляются с действительными службами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Это может быть полезно, когда службу WCF необходимо разместить без обязательного выделения физического файла или ресурса или к службам необходимо получать доступ по URL-адресам, не содержащим файлов, например HTML или ASPX. Этот образец показывает использование класса <xref:System.Web.Routing.RouteTable> для создания виртуальных URI-адресов, связанных с выполняющимися службами, которые определены в файле global.asax. В данном примере с помощью WCF создаются два RSS-канала: канал `movies` и канал `channels`. URL-адреса для запуска служб не содержат расширений и зарегистрированы в `Application_Start` метод `Global` класс, производный от <xref:System.Web.HttpApplication.Application_Start> класса.  
  
> [!NOTE]
>  Классы в пространстве имен <xref:System.Web.Routing> работают только со службами, размещаемыми по протоколу HTTP.  
  
> [!NOTE]
>  Этот образец работает лишь в [!INCLUDE[iisver](../../../../includes/iisver-md.md)], так как [!INCLUDE[iis60](../../../../includes/iis60-md.md)] использует другой метод поддержки URL-адресов без расширений файлов.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebRoutingIntegration`  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл WebRoutingIntegration.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Нажмите клавишу F5, чтобы выполнить решение и запустить веб-сервер разработки.  
  
     Отобразится список каталогов для образца. Обратите внимание, что файлы с расширением SVC отсутствуют.  
  
3.  В адресной строке добавьте в URL-адрес слово `movies` (он будет выглядеть как http://localhost:[порт]/movies) и нажмите клавишу ВВОД.  
  
     В браузере откроется пакет фильмов.  
  
4.  В адресной строке добавьте в URL-адрес слово `channels` (он будет выглядеть как http://localhost:[порт]/channels) и нажмите клавишу ВВОД.  
  
     В браузере откроется пакет каналов.  
  
5.  Закройте веб-браузер, нажав клавиши ALT+F4.  
  
     Если на сервере разработки не прекратил работу, щелкните правой кнопкой мыши значок области уведомлений и выберите **остановить**.  
  
#### <a name="to-use-this-sample-when-hosted-in-iis"></a>Использование этого образца в случае размещения на IIS  
  
1.  Откройте файл WebRoutingIntegration.sln в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Постройте проект, нажав клавиши CTRL+SHIFT+B.  
  
3.  Создайте веб-приложение в Диспетчере служб IIS.  
  
    1.  В диспетчере служб IIS щелкните правой кнопкой мыши **веб-сайт по умолчанию** и выберите **добавить приложение**.  
  
    2.  Для **псевдоним**, введите в `WebRoutingIntegration`.  
  
    3.  Для **физический путь**, укажите служебную папку внутри проекта.  
  
    4.  Press **OK**.  
  
4.  При запуске приложения, щелкнув правой кнопкой мыши веб-приложение и выбрав **управление приложением** и затем **Обзор**.  
  
5.  В адресной строке добавьте в URL-адрес слово `movies` (он будет выглядеть как http://localhost:[порт]/movies) и нажмите клавишу ВВОД.  
  
     В браузере откроется пакет фильмов.  
  
6.  В адресной строке добавьте в URL-адрес слово `channels` (он будет выглядеть как http://localhost:[порт]/channels) и нажмите клавишу ВВОД.  
  
     В браузере откроется пакет каналов.  
  
7.  Закройте веб-браузер, нажав клавиши ALT+F4.  
  
 Этот образец демонстрирует, что уровень размещения может взаимодействовать с классами в пространстве имен <xref:System.Web.Routing> для маршрутизации запросов служб, размещенных через протокол HTTP.  
  
> [!NOTE]
>  Обновите версию пула приложений по умолчанию до [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], если установлена версия 2.  
  
## <a name="see-also"></a>См. также  
 [Образцы размещения и сохраняемости образцы](http://go.microsoft.com/fwlink/?LinkId=193961)
