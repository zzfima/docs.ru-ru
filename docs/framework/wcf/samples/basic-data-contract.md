---
title: "Базовый контракт данных | Microsoft Docs"
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
  - "Контракт данных"
ms.assetid: b124e9e0-cb73-4ae0-b9c3-e6cdf5eced98
caps.latest.revision: 37
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 37
---
# Базовый контракт данных
Этот образец демонстрирует реализацию контракта данных.Контракты данных позволяют передавать структурированные данные в службы и из служб.Этот образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), однако в нем вместо базовых числовых типов используются комплексные числа.  
  
 В этом образце служба размещается в службах IIS, а клиентом является консольное приложение \(EXE\).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В контракте службы для этой службы используются комплексные числа, как показано в следующем образце кода.  
  
```  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
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
  
 К определению класса `ComplexNumber` применены атрибуты <xref:System.Runtime.Serialization.DataContractAttribute>и <xref:System.Runtime.Serialization.DataMemberAttribute>, чтобы указать, какие поля класса могут быть переданы по линии связи между клиентом и службой, как показано в следующем образце кода.  
  
```  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class ComplexNumber  
{  
    [DataMember]  
    public double Real = 0.0D;  
    [DataMember]  
    public double Imaginary = 0.0D;  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
  
```  
  
 Реализация службы вычисляет и возвращает соответствующий результат, принимая и возвращая числа типа `ComplexNumber`.  
  
```  
// This is the service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
  
    public ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real - n2.Real, n1.Imaginary -   
                                                     n2.Imaginary);  
    }  
    public ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2)  
    {  
        double real1 = n1.Real * n2.Real;  
        double imaginary1 = n1.Real * n2.Imaginary;  
        double imaginary2 = n2.Real * n1.Imaginary;  
        double real2 = n1.Imaginary * n2.Imaginary * -1;  
        return new ComplexNumber(real1 + real2, imaginary1 +   
                                                 imaginary2);  
    }  
  
    public ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2)  
    {  
         ComplexNumber conjugate =   
              new ComplexNumber(n2.Real, -1*n2.Imaginary);  
         ComplexNumber numerator = Multiply(n1, conjugate);  
         ComplexNumber denominator = Multiply(n2, conjugate);  
         return new ComplexNumber(numerator.Real / denominator.Real,  
                                               numerator.Imaginary);  
    }  
}  
  
```  
  
 Реализация клиента также оперирует комплексными числами.И контракт службы, и контракт данных определены в исходном файле generatedClient.cs, который формируется с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из метаданных службы.  
  
```  
// Create a client.  
DataContractCalculatorClient client = new DataContractCalculatorClient();  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();   
value1.Real = 1;   
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();   
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = proxy.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
      value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
      result.Real, result.Imaginary);   
    …  
}  
  
```  
  
 При выполнении образца запросы и отклики операции отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 41i  
  
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
>  `<Iдиск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Data\Basic`  
  
## См. также