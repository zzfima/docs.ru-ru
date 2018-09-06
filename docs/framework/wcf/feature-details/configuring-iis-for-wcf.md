---
title: Настройка IIS 7.0 для Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 13fd068f7a058a0fbf4e15fc99a8de91671fb2d5
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44033181"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Настройка IIS 7.0 для Windows Communication Foundation

Службы IIS 7.0 имеют модульную архитектуру, что позволяет выборочно устанавливать необходимые компоненты. Эта архитектура основана на построенной на базе манифестов технологии разбиения на компоненты, появившейся в [!INCLUDE[wv](../../../../includes/wv-md.md)]. Существует более чем из 40 отдельных функциональных компонентов IIS 7.0, которая может устанавливаться независимо друг от друга. Это позволяет ИТ-специалистам легко настраивать службы в соответствии с конкретными требованиями. В этом разделе описывается настройка IIS 7.0 для использования с Windows Communication Foundation (WCF) и определить, какие компоненты являются обязательными.

## <a name="minimal-installation-installing-was"></a>Минимальная установка: установка службы WAS
 Минимальная установка всего пакета IIS 7.0 — установить службу активации процессов Windows (WAS). Это независимый компонент и это единственный компонент с помощью IIS 7.0, которая доступна для всех [!INCLUDE[wv](../../../../includes/wv-md.md)] операционных систем (Home Basic, Home Premium, Business и Ultimate и Enterprise).

 С помощью панели управления щелкните **программы** и нажмите кнопку **или отключение компонентов Windows включить** в категории **программы и компоненты**, компоненты WAS появится в список, как показано на следующем рисунке.

 ![Включение функции или отключить диалоговое окно](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")

 Этот компонент включает следующие подкомпоненты:

-   Среда .NET Environment

-   Интерфейсы API настройки

-   Модель процессов

 Если вы выберите корневой узел WAS, только **модель процесса** будет выбран по умолчанию. Обратите внимание, что при такой установке устанавливается только служба WAS, поскольку поддержка веб-сервера отсутствует.

 Чтобы обеспечить WCF или какой-либо работы приложения ASP.NET, проверьте **среды .NET** флажок. Это означает, что все компоненты WAS требуются WCF и ASP.NET, хорошо работать. Они автоматически выбираются при установке какого либо из этих компонентов.

## <a name="iis-70-default-installation"></a>Службы IIS 7.0: установка по умолчанию
 Проверив **Internet Information Services** компонентов, некоторые подкомпоненты проверяются автоматически, как показано на следующем рисунке.

 ![Параметры по умолчанию для компонентов IIS 7.0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")

 Это установка по умолчанию службы IIS 7.0. При такой установке IIS 7.0 можно использовать для статического содержимого службы (например, HTML-страниц и другим содержимым). Тем не менее нельзя запускать приложения ASP.NET или CGI или размещать службы WCF.

## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: установка с поддержкой ASP.NET
 Необходимо установить ASP.NET, чтобы работать на IIS 7.0 ASP.NET. После проверки **ASP.NET**, экран должен выглядеть как на следующем рисунке.

 ![Asp.NET обязательные параметры](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")

 Это минимальную среду для приложений WCF и ASP.NET в IIS 7.0.

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: установка с компонентами совместимости с IIS 6.0
 При установке IIS 7.0 в системе с Visual Studio 2005 или некоторые другие сценарии автоматизации или инструменты (например, Adsutil.vbs), которые настраивают виртуальные приложения, использующие API метабазы IIS 6.0, убедитесь, что установлен флажок IIS 6.0 **средств работы со сценариями**. При этом автоматически проверяется другие компоненты узла IIS 6.0 **совместимость управления**. На следующем рисунке показан экран, после этого:

 ![Параметры совместимости служб IIS 6.0 управления](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")

 При такой установке имеется все необходимое для использования функций IIS 7.0, ASP.NET и WCF и примеры, доступные в Интернете.

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

- [Архитектура активации WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [Настройка WAS для использования с WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Практическое руководство. Установка и настройка компонентов активации WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [Функции размещения фабрики приложений Windows Server](https://go.microsoft.com/fwlink/?LinkId=201276)
