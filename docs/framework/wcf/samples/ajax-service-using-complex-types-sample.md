---
title: Образец службы AJAX, использующей сложные типы
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 4574e5d33ebed7184e229c71e03496db34a95575
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415657"
---
# <a name="ajax-service-using-complex-types-sample"></a>Образец службы AJAX, использующей сложные типы
В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания служб ASP.NET асинхронных скриптов JavaScript и XML (AJAX), создающей экземпляры сложных типов и отправляющей их между службой и клиентом как нотации объектов JavaScript (JSON). К службе AJAX можно обращаться с помощью кода JavaScript из веб-браузера. Этот пример основан на [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образца.  
  
 Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX с помощью <xref:System.Web.UI.ScriptManager> элемента управления. Пример использования WCF с ASP.NET AJAX, см. в разделе [образцы AJAX](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Служба в следующем примере — это служба WCF без написания кода относящегося к AJAX. Поскольку атрибут <xref:System.ServiceModel.Web.WebGetAttribute> не применяется, используется HTTP-команда по умолчанию ("POST"). Служба имеет одну операцию, `DoMath`, возвращающую сложный тип с именем `MathResult`. Сложный тип является стандартным типом контракта данных, также не содержащим код, относящийся к AJAX.  

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
  
 Клиентская веб-страница ComplexTypeClientPage.aspx содержит код ASP.NET и JavaScript для вызова службы, когда пользователь щелкает **выполнить расчет** кнопку на странице. Код для вызова службы создает тело JSON и отправляет его с помощью HTTP POST, аналогичную [служба AJAX с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) образца.  
  
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
  
2.  Построение решения complextypeajaxservice.sln, описанное в разделе [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите к http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (не открывайте ComplexTypeClientPage.aspx в браузере из каталога проекта).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a>См. также  
 [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
