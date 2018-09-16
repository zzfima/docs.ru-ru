---
title: Транспорт и кодировка пользовательской привязки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: ee15fd37390f8bf4ca3bc287f9a3dbd5f8ebd935
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668682"
---
# <a name="custom-binding-transport-and-encoding"></a>Транспорт и кодировка пользовательской привязки
Пользовательская привязка определяется упорядоченным списком отдельных элементов привязки. Этот образец демонстрирует, как настроить пользовательскую привязку с различными элементами транспорта и кодирования сообщений.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец основан на [резидентного размещения](../../../../docs/framework/wcf/samples/self-host.md), был изменен, чтобы настроить три конечных точек для поддержки транспортов HTTP, TCP и NamedPipe с помощью пользовательских привязок. Конфигурация клиента была изменена аналогичным образом, а код клиента изменен для взаимодействия с каждой из этих трех конечных точек.  
  
 Этот образец демонстрирует, как настроить пользовательскую привязку, поддерживающую определенные транспорт и кодирование сообщений. Это достигается путем настройки транспорта и кодирования сообщений для элемента `binding`. Порядок элементов привязки имеет большое значение при определении пользовательской привязки, так как каждый элемент представляет уровень в стеке каналов (см. в разделе [пользовательских привязок](../../../../docs/framework/wcf/extending/custom-bindings.md)). В этом образце настраиваются три пользовательские привязки: транспорт HTTP с текстовым кодированием, транспорт TCP с текстовым кодированием и транспорт NamedPipe с двоичным кодированием.  
  
 Конфигурация службы определяет пользовательскую привязку следующим образом:  
  
```xml  
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
  
 При выполнении образца запросы и ответы операций отображаются в окнах консоли как службы, так и клиента. Клиент взаимодействует с каждой из трех конечных точек, обращаясь сначала к HTTP, затем к TCP и, наконец, к NamedPipe. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
 Привязка `namedPipeTransport` не поддерживает операции между компьютерами. Она служит только для связи на одном компьютере. Поэтому при выполнении этого образца на нескольких компьютерах закомментируйте следующие строки в файле кода клиента:  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на C#, C++ или Visual Basic .NET, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
  
## <a name="see-also"></a>См. также
