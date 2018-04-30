---
title: Поддержка POCO
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9c67b39c8d3c48281eb0ec9c360de7eaff1cfad6
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="poco-support"></a>Поддержка POCO
В этом образце демонстрируется поддержка сериализации непомеченных типов, т. е. типов, к которым не применены атрибуты сериализации. Иногда такие типы называют типами POCO (Plain Old CLR Object). Тип <xref:System.Runtime.Serialization.DataContractSerializer> определяет контракт данных для всех открытых непомеченных типов, имеющих конструктор по умолчанию. Контракты данных позволяют передавать структурированные данные в службы и из служб. Дополнительные сведения о неотмеченных типах см. в разделе [сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), но использует комплексные числа вместо числовых типов-примитивов. Аналогично [базовый контракт данных](../../../../docs/framework/wcf/samples/basic-data-contract.md) выборки, за исключением того, что <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> атрибуты не используются.  
  
 Клиентом является консольное приложение (EXE), а служба размещается в службах Internet Information Services (IIS).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Класс `ComplexNumber` используется классом `ServiceContract`. У типа `ComplexNumber` нет атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, как показано в следующем образце кода. По умолчанию все открытые свойства и поля сериализуются.  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) Чтобы загрузить все [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 [Сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md)
