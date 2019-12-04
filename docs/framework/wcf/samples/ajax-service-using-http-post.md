---
title: Служба AJAX с использованием HTTP POST
ms.date: 03/30/2017
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
ms.openlocfilehash: 560739c576965d597010a6885b53c7905aaeb8e7
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716185"
---
# <a name="ajax-service-using-http-post"></a>Служба AJAX с использованием HTTP POST

В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания асинхронной службы JavaScript и XML (AJAX) ASP.NET, использующей HTTP POST. Обращаться к службе AJAX можно с использованием кода JavaScript из клиента на основе веб-браузера. Этот пример основан на образце [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) ; Единственное различие между двумя примерами — использование HTTP POST вместо HTTP GET.

Поддержка AJAX в Windows Communication Foundation (WCF) оптимизирована для использования с ASP.NET AJAX через элемент управления `ScriptManager`. Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

Служба в следующем примере представляет собой службу WCF без кода, зависящего от AJAX.

Если атрибут <xref:System.ServiceModel.Web.WebInvokeAttribute> применяется к операции или атрибут <xref:System.ServiceModel.Web.WebGetAttribute> не применяется, используется HTTP-команда по умолчанию (POST). Запросы POST строить тяжелее, чем запросы GET, однако они не кэшируются; запросы POST следует использовать для всех операций, в которых нельзя использовать кэширование.

```csharp
[ServiceContract(Namespace = "PostAjaxService")]
public interface ICalculator
{
    [WebInvoke]
    double Add(double n1, double n2);
    //Other operations omitted…
}
```

Создайте конечную точку AJAX в службе с помощью <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> точно так же, как в образце базовой службы AJAX.

В отличие от запросов GET вызывать службы POST из браузера нельзя. Например, переход к `http://localhost/ServiceModelSamples/service.svc/Add?n1=100&n2=200` приведет к ошибке, так как служба POST ожидает, что параметры `n1` и `n2` отправляются в тексте сообщения в формате JSON, а не в URL-адресе.

Клиентская веб-страница PostAjaxClientPage.aspx содержит код ASP.NET для вызова службы, когда пользователь нажимает одну из кнопок операций на странице. Служба реагирует так же, как и в образце [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) , с запросом GET.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`

## <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что инструкции по установке выполняются [однократным образом для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Создайте решение Постажакссервице. sln, как описано в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Перейдите к `http://localhost/ServiceModelSamples/PostAjaxClientPage.aspx` (не открывайте Постажаксклиентпаже. aspx в браузере из каталога проекта).
