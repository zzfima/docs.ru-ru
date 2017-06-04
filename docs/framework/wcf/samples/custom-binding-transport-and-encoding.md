---
title: "Транспорт и кодировка пользовательской привязки | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Транспорт и кодировка пользовательской привязки
Пользовательская привязка определяется упорядоченным списком отдельных элементов привязки.Этот образец демонстрирует, как настроить пользовательскую привязку с различными элементами транспорта и кодирования сообщений.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец основан на образце [Резидентное размещение](../../../../docs/framework/wcf/samples/self-host.md) и изменен, чтобы настроить три конечные точки для поддержки транспортов HTTP, TCP и NamedPipe с пользовательскими привязками.Конфигурация клиента была изменена аналогичным образом, а код клиента изменен для взаимодействия с каждой из этих трех конечных точек.  
  
 Этот образец демонстрирует, как настроить пользовательскую привязку, поддерживающую определенные транспорт и кодирование сообщений.Это достигается путем настройки транспорта и кодирования сообщений для элемента `binding`.Порядок элементов привязки имеет большое значение при определении пользовательской привязки, поскольку каждый элемент представляет уровень в стеке каналов \(см. раздел [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)\).В этом образце настраиваются три пользовательские привязки: транспорт HTTP с текстовым кодированием, транспорт TCP с текстовым кодированием и транспорт NamedPipe с двоичным кодированием.  
  
 Конфигурация службы определяет пользовательскую привязку следующим образом:  
  
```  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding   
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.Клиент взаимодействует с каждой из трех конечных точек, обращаясь сначала к HTTP, затем к TCP и, наконец, к NamedPipe.Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
 Привязка `namedPipeTransport` не поддерживает операции между компьютерами.Она служит только для связи на одном компьютере.Поэтому при выполнении этого образца на нескольких компьютерах закомментируйте следующие строки в файле кода клиента:  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
>  Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы выполнить построение версии решения для языка C\#, C\+\+ или Visual Basic .NET, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
  
## См. также