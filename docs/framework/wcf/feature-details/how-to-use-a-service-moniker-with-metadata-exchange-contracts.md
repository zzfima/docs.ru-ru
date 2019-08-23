---
title: Практическое руководство. Использование моникера службы с контрактами обмена метаданными
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 00aa1bbde95c0636391f213f830fc67b2dedf459
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968793"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Практическое руководство. Использование моникера службы с контрактами обмена метаданными
После разработки некоторых новых служб WCF вы можете решить, что они могут вызывать эти службы из сценария или приложения Visual Basic 6,0. Одним из способов является создание клиентской сборки WCF, регистрация сборки в COM, установка сборки в GAC, а также ссылки на типы COM из кода Visual Basic. При распространении приложения потребуется также распространять клиентскую сборку WCF. Затем пользователь должен будет зарегистрировать клиентскую сборку WCF с помощью COM и разместить ее в глобальном кэше сборок. COM-взаимодействие WCF также позволяет выполнять одни и те же вызовы служб, не полагаясь на клиентскую сборку WCF. Моникер WCF позволяет вызывать любую службу WCF на любом языке, совместимом с COM (Visual Basic, VBScript, Visual Basic для приложений (VBA) и т. д.), указывая URI конечной точки обмена метаданными (MEX), который моникер службы использует для извлечения типа. сведения о службе. В этом разделе описывается, как вызвать пример начало работы WCF с помощью моникера WCF, который указывает конечную точку обмена метаданными.  
  
> [!NOTE]
> Типы, определенные клиентской сборкой WCF, никогда не создаются. Сборка используется только для метаданных.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Использование моникера службы с адресом обмена метаданными (Mex)  
  
1. Создайте пример начало работы и используйте Internet Explorer, чтобы перейти к своему URL- http://localhost/ServiceModelSamples/Service.svc) адресу (чтобы убедиться, что служба работает).  
  
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
    > Вызываемая служба должна экспонировать конечную точку обмена метаданными (Mex) в моникер, чтобы прочитать метаданные из службы. Дополнительные сведения см. в разделе [Практическое руководство. Публикация метаданных для службы с помощью файла](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)конфигурации.  
  
    > [!NOTE]
    > Если моникер сформирован неправильно или служба недоступна, при вызове `GetObject` будет возвращена ошибка "Синтаксическая ошибка".  При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Использовать моникер службы Windows Communication Foundation без регистрации](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [Практическое руководство. Использование моникера службы с контрактами WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
