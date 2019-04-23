---
title: Практическое руководство. Использование моникера службы с контрактами обмена метаданными
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 367cbd4a2bfbde3d4ab0a74eeeaf5d5f5662ec27
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319837"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Практическое руководство. Использование моникера службы с контрактами обмена метаданными
После разработки некоторые новые службы WCF, вы решите, что вы хотите иметь возможность вызывать эти службы из файла скрипта или приложения Visual Basic 6.0. Один из методов можно создать сборку клиента WCF, Зарегистрируйте сборку с помощью COM, установите сборку в глобальный кэш СБОРОК и затем ссылаться на типы COM из кода Visual Basic. При распространении приложения, необходимо распространить клиента WCF к сборке. Затем пользователь должен будет зарегистрировать клиентскую сборку WCF с помощью COM и разместить ее в глобальном кэше сборок. COM-взаимодействия WCF также позволяет сделать вызовы той же службы, не полагаясь на клиентскую сборку WCF. Моникера WCF позволяет вызывать любую службу WCF из любого COM-совместимого языка (Visual Basic, VBScript, Visual Basic for Applications (VBA) и т. д.), указав конечную точку метаданных exchange (Mex) URI, моникер служб использует для извлечения типа сведения о службе. В этом разделе описывается, как вызывать пример Приступая к работе с WCF, с помощью моникера WCF, указывающего конечную точку обмена метаданными.  
  
> [!NOTE]
>  Фактически никогда не создаются типы, определенные в сборке клиента WCF. Сборка используется только для метаданных.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Использование моникера службы с адресом обмена метаданными (Mex)  
  
1. Построение образца Приступая к работе и перейдите по URL-адресу с помощью Internet Explorer (http://localhost/ServiceModelSamples/Service.svc) чтобы убедиться, что служба работает.  
  
2. Создайте скрипт Visual Basic или приложение Visual Basic, содержащее следующий код:  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. Запустите приложение или скрипт Visual Basic.  
  
    > [!NOTE]
    >  Вызываемая служба должна экспонировать конечную точку обмена метаданными (Mex) в моникер, чтобы прочитать метаданные из службы. Дополнительные сведения см. в разделе [Как Публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    >  Если моникер сформирован неправильно или служба недоступна, при вызове `GetObject` будет возвращена ошибка "Синтаксическая ошибка".  При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [Практическое руководство. Использование моникера службы с контрактами WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
