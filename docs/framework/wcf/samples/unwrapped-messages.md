---
title: "Сообщения без оболочки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# Сообщения без оболочки
В этом образце показаны сообщения без оболочки.По умолчанию тело сообщения форматируется так, чтобы параметры, которые передаются операциям службы, находились в оболочке.В следующем образце показано заключенное в оболочку сообщение запроса `Add` для службы `ICalculator`.  
  
```  
<s:Envelope   
    xmlns:s=http://www.w3.org/2003/05/soap-envelope  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
  
```  
  
 Элемент `<Add>` в теле сообщения выступает в роли оболочки для параметров `n1` и `n2`.В следующем образце показано эквивалентное сообщение без оболочки.  
  
```  
<s:Envelope   
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"   
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
</MessageLogTraceRecord>  
  
```  
  
 В этом сообщении параметры `n1` и `n2` не помещены в элемент\-оболочку, а являются непосредственными дочерними элементами элемента soap body.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца расположены в конце этого раздела.  
  
 В этом образце сообщение без оболочки создается путем применения атрибута <xref:System.ServiceModel.MessageContractAttribute> к типу параметра и типу возвращаемого значения операции службы, как показано в следующем образце кода.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 Для просмотра всех отправляемых и получаемых сообщений в этом образце используется трассировка.Кроме того, для привязки <xref:System.ServiceModel.WSHttpBinding> не были настроены параметры безопасности, чтобы сократить число заносимых в журнал сообщений.  
  
 Полученный журнал трассировки \(c:\\logs\\Message.log\) можно просмотреть с помощью средства [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).Чтобы увидеть содержимое сообщения, выберите **Сообщение** в правой и левой областях средства Service Trace Viewer.Этот образец настроен таким образом, чтобы журналы трассировки сохранялись в папке C:\\LOGS.Создайте эту папку перед выполнением образца и предоставьте сетевой службе пользователя разрешение на запись в эту папку.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Создайте каталог C:\\LOGS для регистрации сообщений.Предоставьте сетевой службе пользователя разрешение на запись в этот каталог.  
  
3.  Чтобы выполнить построение версии решения для языка C\# или Visual Basic .NET, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
  
## См. также