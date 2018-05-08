---
title: Практическое руководство. Использование моникера службы с контрактами обмена метаданными
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 6265860c2e1efb2f74a0243157a223a33889629a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Практическое руководство. Использование моникера службы с контрактами обмена метаданными
Разработав несколько новых служб WCF, может решить, требуется иметь возможность вызова данных служб из скрипта или приложения Visual Basic 6.0. Один из методов можно создать сборку клиента WCF, Зарегистрируйте сборку с помощью COM, установка сборки в глобальном кэше СБОРОК и затем ссылаться на типы COM из кода на Visual Basic. При распространении приложения, необходимо распространить ее клиента WCF. Затем пользователь должен будет зарегистрировать клиентскую сборку WCF с помощью COM и разместить ее в глобальном кэше сборок. WCF COM-взаимодействие также позволяет принимать вызовы той же службы, не полагаясь на клиентскую сборку WCF. Моникер WCF позволяет вызывать любую службу WCF из любого COM-совместимого языка (Visual Basic, VBScript, Visual Basic для приложений (VBA) и т. д.), указав конечную точку обмена метаданными URI, который использует моникера службы для извлечения типа сведения о службе. Описывается, как вызвать образец WCF Приступая к работе с помощью моникера WCF, указывающего конечную точку обмена метаданными.  
  
> [!NOTE]
>  Фактически не создаются экземпляры типов, определенных в сборке клиента WCF. Сборка используется только для метаданных.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Использование моникера службы с адресом обмена метаданными (Mex)  
  
1.  Построение образца Приступая к работе и использовать Internet Explorer, чтобы перейти к его URL-адрес (http://localhost/ServiceModelSamples/Service.svc) чтобы убедиться, что служба работает.  
  
2.  Создайте скрипт Visual Basic или приложение Visual Basic, содержащее следующий код:  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  Запустите приложение или скрипт Visual Basic.  
  
    > [!NOTE]
    >  Вызываемая служба должна экспонировать конечную точку обмена метаданными (Mex) в моникер, чтобы прочитать метаданные из службы. Дополнительные сведения см. в разделе [как: публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    >  Если моникер сформирован неправильно или служба недоступна, при вызове `GetObject` будет возвращена ошибка "Синтаксическая ошибка".  При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [Практическое руководство. Использование моникера службы с контрактами WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
