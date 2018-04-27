---
title: Образец службы AJAX, использующей сложные типы
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b821a252e202f0fef719e1545b38b4423237d0c7
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="ajax-service-using-complex-types-sample"></a>Образец службы AJAX, использующей сложные типы
В данном примере демонстрируется использование [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для создания службы ASP.NET с асинхронными скриптами JavaScript и XML (AJAX), создающей экземпляры сложных типов и отправляющей их между службой и клиентом как нотации объектов JavaScript (JSON). К службе AJAX можно обращаться с помощью кода JavaScript из веб-браузера. Этот пример основан на [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образца.  
  
 Поддержка технологии AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] оптимизирована для использования с ASP.NET AJAX с помощью элемента управления <xref:System.Web.UI.ScriptManager>. Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX, в разделе [примеров AJAX](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Служба в следующем примере является службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] без кода, относящегося к AJAX. Поскольку атрибут <xref:System.ServiceModel.Web.WebGetAttribute> не применяется, используется HTTP-команда по умолчанию ("POST"). Служба имеет одну операцию, `DoMath`, возвращающую сложный тип с именем `MathResult`. Сложный тип является стандартным типом контракта данных, также не содержащим код, относящийся к AJAX.  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 Создайте конечную точку AJAX в службе с помощью <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> точно так же, как в образце базовой службы AJAX.  
  
 Клиентская веб-страница ComplexTypeClientPage.aspx содержит код ASP.NET и JavaScript для вызова службы, когда пользователь нажимает кнопку **выполнить расчет** кнопку на странице. Код, вызывающий службу, создает тело JSON и отправляет его с помощью HTTP POST, аналогично [AJAX службы с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) образца.  
  
 После успешного вызова службы можно получать доступ к отдельным членам данных (`sum`, `difference`, `product` и `quotient`) в полученном объекте JavaScript.  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Постройте решение ComplexTypeAjaxService.sln, как описано в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите к http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (не открывайте ComplexTypeClientPage.aspx в браузере из каталога проекта).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a>См. также  
 [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
