---
title: Настройка свойств использования и стиля — примеры WCF
ms.date: 03/30/2017
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
ms.openlocfilehash: f92b25144759692c54aa7a1730a9bb85cab4f15f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714428"
---
# <a name="setting-the-use-and-style-properties"></a>Установка свойств Use и Style

В этом образце кода показано, как использовать свойства Use и Style классов <xref:System.ServiceModel.XmlSerializerFormatAttribute> и <xref:System.ServiceModel.DataContractFormatAttribute>. Эти свойства влияют на форматирование сообщений. По умолчанию тело сообщения форматируется с использованием стиля <xref:System.ServiceModel.OperationFormatStyle.Document>. Эти параметры можно задать либо на уровне контракта службы, либо на уровне контракта операции.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

Свойство <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> определяет форматирование метаданных WSDL службы. Допустимые значения: <xref:System.ServiceModel.OperationFormatStyle.Document> и <xref:System.ServiceModel.OperationFormatStyle.Rpc>. Стиль RPC означает, что WSDL-представление сообщений, которыми осуществляется обмен в ходе операции, содержит такие же параметры, как при удаленном вызове процедур. Ниже приведен пример.

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="n1" type="xsd:double"/>
  <wsdl:part name="n2" type="xsd:double"/>
</wsdl:message>
```

При задании для стиля значения <xref:System.ServiceModel.OperationFormatStyle.Document> WSDL-представление будет содержать единственный элемент, представляющий документ, которым осуществляется обмен в ходе операции, как показано в следующем примере.

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="parameters" element="tns:Add"/>
</wsdl:message>
```

Свойство <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> определяет формат сообщения. Возможные значения: <xref:System.ServiceModel.OperationFormatUse.Literal> и <xref:System.ServiceModel.OperationFormatUse.Encoded>. Значение по умолчанию: <xref:System.ServiceModel.OperationFormatUse.Literal>. Значение Literal означает, что сообщение представляет собой литеральный экземпляр схемы в WSDL, как показано в следующем примере стиля Document/Literal.

```xml
<Add xmlns="http://Microsoft.ServiceModel.Samples">
  <n1>100</n1>
  <n2>15.99</n2>
</Add>
```

«Encoded» (закодировано) означает, что схемы в WSDL являются абстрактными спецификациями, которые кодируются в соответствии с правилами в разделе 5 спецификации SOAP 1.1. Далее приведен пример RPC/Encoded.

```xml
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">
  <n1 xsi:type="xsd:double" xmlns="">100</n1>
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>
</q1:Add>
```

Профиль WS-I Basic Profile 1.0 запрещает использование стиля <xref:System.ServiceModel.OperationFormatUse.Encoded>, поэтому его следует использовать, только когда того требуют службы, созданные по устаревшим стандартам. Формат сообщений `Encoded` доступен только при использовании сериализатора XmlSerializer.

Для просмотра отправляемых и получаемых сообщений Этот образец основан на [трассировке и регистрации сообщений](tracing-and-message-logging.md). В конфигурацию службы и исходный код внесены изменения, позволяющие использовать трассировку и журнал сообщений. Кроме того, привязка <xref:System.ServiceModel.WSHttpBinding> настроена без использования средств безопасности, что позволяет просматривать сообщения в журнале в формате без шифрования. Результирующие журналы трассировки (System. ServiceModel. E2E и Message. log) должны быть просмотрены с помощью [средства Service Trace Viewer (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md). В конфигурации задана следующая папка для создания трассировок: C:\LOGS. Создайте эту папку, прежде чем выполнять код из этого образца. Чтобы просмотреть содержимое сообщения в средстве просмотра трассировки, выберите **сообщения** в левой и правой панелях инструмента.

В следующем примере кода приведен контракт службы, в котором свойству <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> задано значение <xref:System.ServiceModel.OperationFormatUse>, и вместо формата тела сообщения по умолчанию (<xref:System.ServiceModel.OperationFormatStyle>) задан формат <xref:System.ServiceModel.OperationFormatStyle.Document>.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),
XmlSerializerFormat(Style = OperationFormatStyle.Rpc, 
                                 Use = OperationFormatUse.Encoded)]
public interface IUseAndStyleCalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

Чтобы проверить различия между параметрами <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> и <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A>, измените их для службы, заново создайте клиент, выполните пример и просмотрите файл c:\logs\message.logs с помощью средства Service Trace Viewer. Также обратите внимание на влияние на метаданные, просматривая `http://localhost/ServiceModelSamples/service.svc?wsdl`. Метаданные служб обычно подразделяются на несколько страниц. Главная страница WSDL содержит привязки WSDL, но просмотр `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0` для просмотра определений сообщений.

## <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](one-time-setup-procedure-for-the-wcf-samples.md).

2. Создайте каталог C:\LOGS для регистрации сообщений. Предоставьте сетевой службе пользователя разрешение на запись в этот каталог.

3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](running-the-samples.md).

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
> 
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`
