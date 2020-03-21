---
title: Практическое руководство. Размещение службы WCF в IIS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 580b380a6c6349c6a4efa26e3eefe38bd660fa1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184922"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a>Практическое руководство. Размещение службы WCF в IIS
В этой теме излагаются основные шаги, необходимые для создания службы Windows Communication Foundation (WCF), которая размещается в информационных службах Интернета (IIS). Предполагается, что читатель знаком со службами IIS и может использовать средство управления IIS для создания приложений служб IIS и управления такими приложениями. Для получения дополнительной информации о IIS см [Интернет информационных услуг](https://www.iis.net/). Служба WCF, работающая в среде IIS, в полной мере использует такие функции IIS, как переработка процессов, простоя, мониторинг работоспособности процессов и активация на основе сообщений. Для реализации этого варианта размещения требуется правильно настроить службу IIS, но не требуется включать в приложение код размещения. Размещение в службах IIS возможно только при использовании транспорта HTTP.  
  
 Для получения дополнительной информации о том, как взаимодействуют WCF и ASP.NET, см [ASP.NET.](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) Для получения дополнительной информации о настройке безопасности, [см.](../../../../docs/framework/wcf/feature-details/security.md)  
  
 Для исходной копии этого [IIS Hosting Using Inline Code](../../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)примера см.  
  
### <a name="to-create-a-service-hosted-by-iis"></a>Создание службы, размещенной в IIS  
  
1. Убедитесь, что службы IIS установлены и выполняются на компьютере. Для получения дополнительной информации об установке и настройке IIS смотрите [Установка и настройка IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)  
  
2. Создайте новую папку для файлов приложений под названием "IISHostedCalcService", убедитесь, что ASP.NET имеет доступ к содержимому папки, и используйте инструмент управления IIS для создания нового приложения IIS, которое физически находится в этом каталоге приложений. Создайте для каталога приложения псевдоним «IISHostedCalc».  
  
3. Создайте в каталоге приложения новый файл с именем «service.svc». Оторите этот файл, добавив следующий @ServiceHost элемент.  
  
   ```
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. В каталоге приложения создайте подкаталог App_Code.  
  
5. Создайте файл кода с именем Service.cs во вложенном каталоге App_Code.  
  
6. Добавьте следующие операторы using в начало файла Service.cs.  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. Добавьте следующее объявление пространства имен после операторов using.  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. Определите контракт службы в пределах объявления пространства имен, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. Реализуйте контракт службы после определения контракта службы, как показано в следующем коде.  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. Создайте в каталоге приложения файл с именем Web.config и добавьте в него следующий код конфигурации. Во время выполнения инфраструктура WCF использует информацию для построения конечной точки, с помощью которого клиентские приложения могут общаться.  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     В этом примере конечные точки явно задаются в файле конфигурации. Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию. Для получения дополнительной информации о конечных точках по умолчанию, привязки и поведении [см. Упрощенную конфигурацию](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенную конфигурацию для WCF Services.](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)  
  
11. Чтобы проверить правильность размещения службы, откройте экземпляр окна Internet Explorer и перейдите по URL-адресу службы: `http://localhost/IISHostedCalc/Service.svc`.  
  
## <a name="example"></a>Пример  
 Далее представлен полный код службы калькулятора, размещаемой в IIS.  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a>См. также раздел

- [Размещение в службах IIS](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md)
- [Размещение служб](../../../../docs/framework/wcf/hosting-services.md)
- [Службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md)
- [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)
- [Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
