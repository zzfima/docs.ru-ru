---
title: Служба AJAX без конфигурации
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: f722eac27fadbd772b85a638c3c9171c2783a8b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582192"
---
# <a name="ajax-service-without-configuration"></a>Служба AJAX без конфигурации
В этом примере показано, как использовать Windows Communication Foundation (WCF), чтобы создать базовую службу ASP.NET асинхронных скриптов JavaScript и XML (AJAX) (службы, которому можно получить доступ с помощью кода JavaScript из веб-браузера клиента), не применяя никакой конфигурации Параметры. Эта служба использует особый синтаксис в файле .svc для автоматического включения конечной точки AJAX.  
  
 Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX с помощью `ScriptManager` элемента управления. Пример использования WCF с ASP.NET AJAX, см. в разделе [образцы Ajax](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец сформирован на основе службы AJAX, в которой используются сообщения POST протокола HTTP. Как описано в разделе [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) примере <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> используется для размещения службы.  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 Объект <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> автоматически добавляет конечную точку <xref:System.ServiceModel.Description.WebScriptEndpoint> к службе. Если в конфигурацию этой конечной точки не требуется вносить изменения, то раздел `<system.ServiceModel>` из файла Web.config для этой службы может быть полностью удален. Файл Web.config содержит некоторые параметры ASP.NET, которые используются в файле ConfigFreeClientPage.aspx. Если дело обстоит иначе, то удалить можно весь файл Web.config.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены инструкции по установке [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Построение решения ConfigFreeAjaxService.sln, как описано в разделе [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите к `http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx` (не открывайте ConfigFreeClientPage.aspx в браузере из каталога проекта).  
  
> [!NOTE]
>  При выполнении этого примера убедитесь, что анонимный доступ и проверка подлинности Windows не включены одновременно для папки ServiceModelSamples в IIS. Однако если они включены, отключите проверку подлинности Windows. По завершении выполнения примера включите проверку подлинности Windows и выполните "iisreset".  
  
## <a name="see-also"></a>См. также
- [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
