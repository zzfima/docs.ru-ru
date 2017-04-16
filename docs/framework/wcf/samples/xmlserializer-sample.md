---
title: "Образец XmlSerializer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d134453-9a35-4202-ba77-9ca3a65babc3
caps.latest.revision: 23
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 23
---
# Образец XmlSerializer
Данный образец демонстрирует выполнение сериализации и десериализации типов, совместимых с <xref:System.Xml.Serialization.XmlSerializer>.Модуль форматирования [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] по умолчанию является классом <xref:System.Runtime.Serialization.DataContractSerializer>.Класс <xref:System.Xml.Serialization.XmlSerializer> может быть использован для выполнения сериализации и десериализации типов в том случае, когда не может быть использован класс <xref:System.Runtime.Serialization.DataContractSerializer>.Это часто происходит, когда требуется четкий контроль над XML — например, если фрагмент данных должен быть атрибутом XML, а не XML\-элементом.Кроме того, сериализатор <xref:System.Xml.Serialization.XmlSerializer> часто выбирается автоматически при создании клиентов для служб, не относящихся к [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Как показано в следующем образце кода, к интерфейсу должны быть применены атрибуты <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.XmlSerializerFormatAttribute>.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface IXmlSerializerCalculator  
{  
    [OperationContract]  
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);  
}  
  
```  
  
 Общие члены класса `ComplexNumber` сериализуются с помощью <xref:System.Xml.Serialization.XmlSerializer> как атрибуты XML.Сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> не может быть использован для создания данного вида экземпляра XML.  
  
```  
public class ComplexNumber  
{  
    private double real;  
    private double imaginary;  
  
    [XmlAttribute]  
    public double Real  
    {  
        get { return real; }  
        set { real = value; }  
    }  
  
    [XmlAttribute]  
    public double Imaginary  
    {  
        get { return imaginary; }  
        set { imaginary = value; }  
    }  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
    public ComplexNumber()  
    {  
        this.Real = 0;  
        this.Imaginary = 0;  
    }  
  
}  
```  
  
 Реализация службы рассчитывает и возвращает соответствующий результат, принимая и возвращая значения типа `ComplexNumber`.  
  
```  
public class XmlSerializerCalculatorService : IXmlSerializerCalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
    …  
}  
  
```  
  
 Реализация клиента также оперирует комплексными числами.Контракт службы и типы данных определяются во входном файле generatedClient.cs, который был создан с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из метаданных службы.Svcutil.exe может определить, когда контракт не сериализуется с помощью сериализатора <xref:System.Runtime.Serialization.DataContractSerializer>, и в этом случае возвращается к выдаче типов `XmlSerializable`.Если нужно принудительно использовать сериализатор <xref:System.Xml.Serialization.XmlSerializer>, можно указать в средстве Svcutil.exe параметр \/serializer:XmlSerializer \(использование XmlSerializer\).  
  
```  
// Create a client.  
XmlSerializerCalculatorClient client = new  
                         XmlSerializerCalculatorClient();  
  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();  
value1.Real = 1;  
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();  
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = client.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
    value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
    result.Real, result.Imaginary);  
    …  
}  
  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 1.41379310344828i  
  
Press <ENTER> to terminate client.  
```  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Client\Interop\XmlSerializer`  
  
## См. также