---
title: "Пример DataContractSerializer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "модуль форматирования XML"
ms.assetid: e0a2fe89-3534-48c8-aa3c-819862224571
caps.latest.revision: 37
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 37
---
# Пример DataContractSerializer
В образце DataContractSerializer показывается сериализатор <xref:System.Runtime.Serialization.DataContractSerializer>, выполняющий службы общей сериализации и десериализации для классов контракта данных.  В образце создается объект `Record` , сериализуется в поток памяти, который десериализуется в другой объект `Record`, чтобы продемонстрировать использование <xref:System.Runtime.Serialization.DataContractSerializer>.  Затем в образце объект `Record` сериализуется с помощью модуля записи двоичных данных, чтобы продемонстрировать, как этот модуль влияет на сериализацию.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Контракт данных для `Record` показан в следующем образце кода.  
  
```  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
internal class Record  
{  
    private double n1;  
    private double n2;  
    private string operation;  
    private double result;  
  
    internal Record(double n1, double n2, string operation, double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    [DataMember]  
    internal double OperandNumberOne  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [DataMember]  
    internal double OperandNumberTwo  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [DataMember]  
    internal string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]  
    internal double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
  
    public override string ToString()  
    {  
        return string.Format("Record: {0} {1} {2} = {3}", n1,  
            operation, n2, result);  
    }  
}  
```  
  
 Код образца создает объект `Record` с именем `record1`, а затем отображает объект.  
  
```  
Record record1 = new Record(1, 2, "+", 3);  
Console.WriteLine("Original record: {0}", record1.ToString());  
  
```  
  
 После этого в образце используется <xref:System.Runtime.Serialization.DataContractSerializer> для сериализации `record1` в поток памяти.  
  
```  
MemoryStream stream1 = new MemoryStream();  
  
//Serialize the Record object to a memory stream using DataContractSerializer.  
DataContractSerializer serializer = new DataContractSerializer(typeof(Record));  
serializer.WriteObject(stream1, record1);  
  
```  
  
 Затем в образце используется <xref:System.Runtime.Serialization.DataContractSerializer> для десериализации потока памяти в новый объект `Record`, который затем отображается.  
  
```  
stream1.Position = 0;  
  
//Deserialize the Record object back into a new record object.  
Record record2 = (Record)serializer.ReadObject(stream1);  
  
Console.WriteLine("Deserialized record: {0}", record2.ToString());  
  
```  
  
 По умолчанию `DataContractSerializer` кодирует объекты в поток с помощью текстового представления XML.  Однако на кодирование XML можно повлиять, передав его другому модулю записи данных.  В этом образце создается модель записи двоичных данных путем вызова <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>.  Затем этот модуль и объект записи передаются сериализатору при вызове <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>.  Наконец, выполняется очистка модуля записи данных и отчетов согласно размеру потоков.  
  
```  
MemoryStream stream2 = new MemoryStream();  
  
XmlDictionaryWriter binaryDictionaryWriter = XmlDictionaryWriter.CreateBinaryWriter(stream2);  
serializer.WriteObject(binaryDictionaryWriter, record1);  
binaryDictionaryWriter.Flush();  
  
//report the length of the streams  
Console.WriteLine("Text Stream is {0} bytes long", stream1.Length);  
Console.WriteLine("Binary Stream is {0} bytes long", stream2.Length);  
```  
  
 При запуске образца отображаются исходная и десериализованная запись с последующем сравнением длины текстового и двоичного кодирования.  Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Original record: Record: 1 + 2 = 3  
Deserialized record: Record: 1 + 2 = 3  
Text Stream is 233 bytes long  
Binary Stream is 156 bytes long  
  
Press <ENTER> to terminate client.  
```  
  
### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы запустить пример, запустите клиент из командной строки, введя client\\bin\\client.exe.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractSerializer`  
  
## См. также