---
title: "Поддержка POCO | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Поддержка POCO
В этом образце демонстрируется поддержка сериализации непомеченных типов, т. е. типов, к которым не применены атрибуты сериализации. Иногда такие типы называют типами POCO \(Plain Old CLR Object\).Тип <xref:System.Runtime.Serialization.DataContractSerializer> определяет контракт данных для всех открытых непомеченных типов, имеющих конструктор по умолчанию.Контракты данных позволяют передавать структурированные данные в службы и из служб.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о неотмеченных типах см. в разделе [Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 Этот образец основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), однако в нем вместо примитивных числовых типов используются комплексные числа.Кроме того, он похож на образец [Базовый контракт данных](../../../../docs/framework/wcf/samples/basic-data-contract.md) за тем исключением, что в нем не используются атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>.  
  
 Клиентом является консольное приложение \(EXE\), а служба размещается в службах Internet Information Services \(IIS\).  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Класс `ComplexNumber` используется классом `ServiceContract`.У типа `ComplexNumber` нет атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, как показано в следующем образце кода.По умолчанию все открытые свойства и поля сериализуются.  
  
```  
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
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
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## См. также  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>   
 [Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md)