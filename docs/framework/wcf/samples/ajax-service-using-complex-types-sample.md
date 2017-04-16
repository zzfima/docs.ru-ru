---
title: "Образец службы AJAX, использующей сложные типы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Образец службы AJAX, использующей сложные типы
В данном примере демонстрируется использование [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для создания службы ASP.NET с асинхронными скриптами JavaScript и XML \(AJAX\), создающей экземпляры сложных типов и отправляющей их между службой и клиентом как нотации объектов JavaScript \(JSON\).К службе AJAX можно обращаться с помощью кода JavaScript из веб\-браузера.Этот образец построен на основе образца [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md).  
  
 Поддержка технологии AJAX в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] оптимизирована для использования с ASP.NET AJAX с помощью элемента управления <xref:System.Web.UI.ScriptManager>.Пример использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с ASP.NET AJAX см. в разделе [AJAX Samples](http://msdn.microsoft.com/ru-ru/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Служба в следующем примере является службой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] без кода, относящегося к AJAX.Поскольку атрибут <xref:System.ServiceModel.Web.WebGetAttribute> не применяется, используется HTTP\-команда по умолчанию \("POST"\).Служба имеет одну операцию, `DoMath`, возвращающую сложный тип с именем `MathResult`.Сложный тип является стандартным типом контракта данных, также не содержащим код, относящийся к AJAX.  
  
```  
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
  
 Клиентская веб\-страница ComplexTypeClientPage.aspx содержит код ASP.NET и JavaScript для вызова службы, когда пользователь нажимает кнопку **Выполнить расчет** на странице.Код для вызова службы создает тело JSON и отправляет его с помощью HTTP POST, как в примере [Служба AJAX с использованием HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).  
  
 После успешного вызова службы можно получать доступ к отдельным членам данных \(`sum`, `difference`, `product` и `quotient`\) в полученном объекте JavaScript.  
  
```  
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
  
```  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Выполните построение решения ComplexTypeAjaxService.sln, описанное в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Перейдите по адресу http:\/\/localhost\/ServiceModelSamples\/ComplexTypeClientPage.aspx \(не открывайте ComplexTypeClientPage.aspx в браузере из каталога проекта\).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## См. также  
 [Базовая служба AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md)