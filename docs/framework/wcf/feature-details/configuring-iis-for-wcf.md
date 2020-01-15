---
title: Настройка IIS 7.0 для Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1050d395-092e-44d3-b4ba-66be3b039ffb
ms.openlocfilehash: 41eedcf78d8ca6f10fcd0380e43420dcc1b328f1
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964508"
---
# <a name="configuring-internet-information-services-70-for-windows-communication-foundation"></a>Настройка IIS 7.0 для Windows Communication Foundation

Службы IIS 7.0 имеют модульную архитектуру, что позволяет выборочно устанавливать необходимые компоненты. Эта схема основана на новой технологии, управляемой манифестом, которая появилась в Windows Vista. Существует более 40 отдельных компонентов служб IIS 7,0, которые могут быть установлены независимо. Это позволяет ИТ-специалистам легко настраивать службы в соответствии с конкретными требованиями. В этом разделе описано, как настроить IIS 7,0 для использования с Windows Communication Foundation (WCF) и определить, какие компоненты требуются.

## <a name="minimal-installation-installing-was"></a>Минимальная установка: установка службы WAS
 Минимальная установка всего пакета IIS 7,0 заключается в установке службы активации процессов Windows (WAS). WAS — это автономная функция, которая является единственной функцией IIS 7,0, доступной для всех операционных систем Windows Vista (Домашняя базовая, Домашняя расширенная, Business, максимальная и корпоративная).

 На панели управления щелкните **программы** , а затем — **Включение или отключение компонентов Windows** , которые перечислены в разделе **программы и компоненты**, компонент WAS показан в списке, как показано на следующем рисунке.

 ![Диалоговое окно включения или отключения компонентов](../../../../docs/framework/wcf/feature-details/media/wcfc-turnfeaturesonoroffs.gif "wcfc_TurnFeaturesOnOrOffs")

 Этот компонент включает следующие подкомпоненты:

- Среда .NET Environment

- Интерфейсы API настройки

- модель процесса;

 Если выбран корневой узел WAS, по умолчанию проверяется только вложенный узел **модели процесса** . Обратите внимание, что при такой установке устанавливается только служба WAS, поскольку поддержка веб-сервера отсутствует.

 Чтобы сделать WCF или любое приложение ASP.NET работать, установите флажок **среда .NET** . Это означает, что все компоненты WAS необходимы для того, чтобы обеспечить хорошую работу WCF и ASP.NET. Они автоматически выбираются при установке какого либо из этих компонентов.

## <a name="iis-70-default-installation"></a>Службы IIS 7.0: установка по умолчанию
 После проверки функции **службы IIS** некоторые из подузлов автоматически проверяются, как показано на следующем рисунке.

 ![Параметры по умолчанию для компонентов IIS 7,0](../../../../docs/framework/wcf/feature-details/media/wcfc-turningfeaturesonoroff2.gif "wcfc_TurningFeaturesOnOrOff2")

 Это установка IIS 7,0 по умолчанию. С помощью этой установки можно использовать IIS 7,0 для обслуживания статического содержимого (например, HTML-страниц и другого содержимого). Однако вы не можете запускать приложения ASP.NET или CGI или размещать службы WCF.

## <a name="iis-70-installation-with-aspnet-support"></a>IIS 7.0: установка с поддержкой ASP.NET
 Необходимо установить ASP.NET, чтобы сделать ASP.NET работу с IIS 7,0. После проверки **ASP.NET**экран должен выглядеть, как показано на следующем рисунке.

 ![Параметры, обязательные для Asp.NET](../../../../docs/framework/wcf/feature-details/media/wcfc-trunfeaturesonoroff3s.gif "wcfc_TrunFeaturesOnOrOFf3s")

 Это минимальная среда для приложений WCF и ASP.NET для работы в IIS 7,0.

## <a name="iis-70-installation-with-iis-60-compatibility-components"></a>IIS 7.0: установка с компонентами совместимости с IIS 6.0
 При установке IIS 7,0 в системе с Visual Studio 2005 или некоторыми другими скриптами или инструментами автоматизации (например, Adsutil. vbs), которые настраивают виртуальные приложения, использующие API метабазы IIS 6,0, убедитесь, что вы проверите **средства создания скриптов**для служб IIS 6,0. Это автоматически проверяет другие подузлы **совместимости управления**IIS 6,0. На следующем рисунке показан экран после выполнения этой задачи:

 ![Параметры совместимости управления IIS 6,0](../../../../docs/framework/wcf/feature-details/media/scfc-turnfeaturesonoroff5s.gif "scfc_TurnFeaturesOnOrOff5s")

 В этой установке все, что необходимо для использования функций и примеров IIS 7,0, ASP.NET и WCF, доступны в Интернете.

## <a name="request-limits"></a>Пределы запроса
 В Windows Vista с IIS 7 значение параметров `maxUri` и `maxQueryStringSize` изменилось по умолчанию. По умолчанию фильтрация запросов в IIS 7.0 допускает использование URL-адресов длиной 4096 знаков и строк запросов длиной 2048 знаков. Чтобы изменить эти значения по умолчанию, добавьте в файл App.config следующий XML-код.

```xml
 <system.webServer>
    <security>
        <requestFiltering>
            <requestLimits maxUrl="8192" maxQueryString="8192" />
        </requestFiltering>
    </security>
 </system.webServer>
 ```

## <a name="see-also"></a>См. также:

- [Архитектура активации WAS](../../../../docs/framework/wcf/feature-details/was-activation-architecture.md)
- [Настройка WAS для использования с WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Практическое руководство. Установка и настройка компонентов активации WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)
- [Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
