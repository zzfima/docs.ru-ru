---
title: Настройка IIS 7.0 для Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 3e34f46fbf3ccf12c6a89a7cac96143965d958d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491720"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Настройка IIS 7.0 для Windows Communication Foundation
Службы IIS 7.0 имеют модульную архитектуру, что позволяет выборочно устанавливать необходимые компоненты. Эта архитектура основана на построенной на базе манифестов технологии разбиения на компоненты, появившейся в [!INCLUDE[wv](../../../../includes/wv-md.md)]. Имеется более 40 отдельных функциональных компонентов [!INCLUDE[iisver](../../../../includes/iisver-md.md)], которые можно устанавливать независимо друг от друга. Это позволяет ИТ-специалистам легко настраивать службы в соответствии с конкретными требованиями. В этом разделе описывается настройка [!INCLUDE[iisver](../../../../includes/iisver-md.md)] для использования с Windows Communication Foundation (WCF) и определить, какие компоненты не требуются.  
  
## <a name="minimal-installation-installing-was"></a>Минимальная установка: установка службы WAS  
 Минимальная установка пакета [!INCLUDE[iisver](../../../../includes/iisver-md.md)] предполагает установку службы активации Windows (WAS). Служба WAS - это независимый компонент и единственная функция [!INCLUDE[iisver](../../../../includes/iisver-md.md)], доступная во всех версиях операционной системы [!INCLUDE[wv](../../../../includes/wv-md.md)] (Home Basic, Home Premium, Business, Ultimate и Enterprise).  
  
 С помощью панели управления щелкните **программы** и нажмите кнопку **Включение или отключение компонентов** в разделе **программы и компоненты**, компоненты WAS появится в список, как показано на следующем рисунке.  
  
 ![Включить функции или Off диалогового окна](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")  
  
 Этот компонент включает следующие подкомпоненты:  
  
-   Среда .NET Environment  
  
-   Интерфейсы API настройки  
  
-   Модель процессов  
  
 Если вы выберите корневой узел WAS, только **модель процесса** будет выбран по умолчанию. Обратите внимание, что при такой установке устанавливается только служба WAS, поскольку поддержка веб-сервера отсутствует.  
  
 Чтобы WCF или любой [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложения для работы, проверьте **среды .NET** флажок. Это означает, что все компоненты WAS являются обязательными, чтобы сделать WCF и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] работы. Они автоматически выбираются при установке какого либо из этих компонентов.  
  
## <a name="iis-70-default-installation"></a>Службы IIS 7.0: установка по умолчанию  
 Проверив **Internet Information Services** автоматически выбираются некоторые подкомпоненты, как показано на следующем рисунке.  
  
 ![Параметры по умолчанию для компонентов IIS 7.0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")  
  
 Это установка [!INCLUDE[iisver](../../../../includes/iisver-md.md)] по умолчанию. Такая установка позволяет использовать службы [!INCLUDE[iisver](../../../../includes/iisver-md.md)] для работы со статическим содержимым (например, со страницами HTML и другим содержимым). Однако, не могут выполняться [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложений CGI или размещения служб WCF.  
  
## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: установка с поддержкой ASP.NET  
 Чтобы в службах IIS 7.0 работала поддержка [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], необходимо установить [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. После проверки **ASP.NET**, экран должен выглядеть как на следующем рисунке.  
  
 ![Asp.NET обязательные параметры](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")  
  
 Это минимальная среда для обоих WCF и [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] приложений в [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: установка с компонентами совместимости с IIS 6.0  
 При установке [!INCLUDE[iisver](../../../../includes/iisver-md.md)] в системе с Visual Studio 2005 или некоторых других сценариев автоматизации или средства (например, Adsutil.vbs), настройки виртуальных приложений, использующих [!INCLUDE[iis601](../../../../includes/iis601-md.md)] метабазы API-интерфейса, убедитесь, что установлен флажок [!INCLUDE[iis601](../../../../includes/iis601-md.md)]  **Сценариев**. Автоматически проверяет дочерние узлы из [!INCLUDE[iis601](../../../../includes/iis601-md.md)] **совместимость управления**. На следующем рисунке показан экран, соответствующий этой ситуации.  
  
 ![Параметры совместимости служб IIS 6.0 управления](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")  
  
 При такой установке имеется все, что необходимо использовать [!INCLUDE[iisver](../../../../includes/iisver-md.md)], [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и компоненты WCF и образцы, которые доступны в Интернете.  
  
## <a name="request-limits"></a>Ограничения запросов  
 В [!INCLUDE[wv](../../../../includes/wv-md.md)] со службами IIS 7 были изменены значения по умолчанию для параметров `maxUri` и `maxQueryStringSize`. По умолчанию фильтрация запросов в IIS 7.0 допускает использование URL-адресов длиной 4096 знаков и строк запросов длиной 2048 знаков. Чтобы изменить эти значения по умолчанию, добавьте в файл App.config следующий XML-код.  
  
 `<system.webServer>`  
  
 `<security>`  
  
 `<requestFiltering>`  
  
 `<requestLimits maxUrl="8192" maxQueryString="8192" />`  
  
 `</requestFiltering>`  
  
 `</security>`  
  
 `</system.webServer>`  
  
## <a name="see-also"></a>См. также  
 [Архитектура активации WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)  
 [Настройка WAS для использования с WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)  
 [Практическое руководство. Установка и настройка компонентов активации WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
