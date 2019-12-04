---
title: Служба AJAX без конфигурации
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: bf80f00bbca370c973dab9f20024284a465be521
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716195"
---
# <a name="ajax-service-without-configuration"></a>Служба AJAX без конфигурации

В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания базовой асинхронной службы JavaScript и XML (AJAX) ASP.NET (службы, к которой можно получить доступ с помощью кода JavaScript из клиента веб-браузера) без использования конфигурации. Параметры. Эта служба использует особый синтаксис в файле .svc для автоматического включения конечной точки AJAX.

Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX через элемент управления `ScriptManager`. Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](ajax.md).

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

 Этот образец сформирован на основе службы AJAX, в которой используются сообщения POST протокола HTTP. Как описано в примере [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) , <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> используется для размещения службы.

```text
<%ServiceHost
    language=c#
    Debug="true"
    Service="Microsoft.Ajax.Samples.CalculatorService
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"
%>
```

Объект <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> автоматически добавляет конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе. Если в конфигурацию этой конечной точки не требуется вносить изменения, то раздел `<system.ServiceModel>` из файла Web.config для этой службы может быть полностью удален. Файл Web.config содержит некоторые параметры ASP.NET, которые используются в файле ConfigFreeClientPage.aspx. Если дело обстоит иначе, то удалить можно весь файл Web.config.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`

#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что инструкции по установке выполняются в ходе [однократной настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Создайте решение Конфигфриажакссервице. sln, как описано в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

3. Перейдите к `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (не открывайте ConfigFreeClientPage. aspx в браузере в каталоге проекта).

> [!NOTE]
> При выполнении этого примера убедитесь, что анонимный доступ и проверка подлинности Windows не включены одновременно для папки ServiceModelSamples в IIS. Однако если они включены, отключите проверку подлинности Windows. По завершении выполнения примера включите проверку подлинности Windows и выполните "iisreset".

## <a name="see-also"></a>См. также:

- [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
