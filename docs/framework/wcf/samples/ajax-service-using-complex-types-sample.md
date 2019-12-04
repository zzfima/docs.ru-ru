---
title: Образец службы AJAX, использующей сложные типы
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: be8db36be7ed1639d839113174fdb95505466534
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716239"
---
# <a name="ajax-service-using-complex-types-sample"></a>Образец службы AJAX, использующей сложные типы

В этом примере демонстрируется использование Windows Communication Foundation (WCF) для создания асинхронной службы JavaScript и XML (AJAX) ASP.NET, которая создает экземпляры сложных типов и отправляет их между службой и клиентом как нотация объектов JavaScript (JSON). К службе AJAX можно обращаться с помощью кода JavaScript из веб-браузера. Этот пример основан на образце [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) .

Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX через элемент управления <xref:System.Web.UI.ScriptManager>. Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](ajax.md).

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

Служба в следующем примере представляет собой службу WCF без кода, зависящего от AJAX. Поскольку атрибут <xref:System.ServiceModel.Web.WebGetAttribute> не применяется, используется HTTP-команда по умолчанию ("POST"). Служба имеет одну операцию, `DoMath`, возвращающую сложный тип с именем `MathResult`. Сложный тип является стандартным типом контракта данных, также не содержащим код, относящийся к AJAX.

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

Клиентская веб-страница Комплекстипеклиентпаже. aspx содержит код ASP.NET и JavaScript для вызова службы, когда пользователь нажимает кнопку **выполнить вычисление** на странице. Код для вызова службы создает тело JSON и отправляет его с помощью HTTP POST, аналогично [службе AJAX с примером HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) .

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

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Создайте решение Комплекстипеажакссервице. sln, как описано в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Перейдите к `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (не открывайте Комплекстипеклиентпаже. aspx в браузере из каталога проекта).

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`

## <a name="see-also"></a>См. также:

- [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
