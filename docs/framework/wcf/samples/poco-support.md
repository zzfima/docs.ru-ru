---
title: Поддержка POCO
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: ab95469afa53bd0b27efc451875d4912db74a45a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="poco-support"></a><span data-ttu-id="6ccac-102">Поддержка POCO</span><span class="sxs-lookup"><span data-stu-id="6ccac-102">POCO Support</span></span>
<span data-ttu-id="6ccac-103">В этом образце демонстрируется поддержка сериализации непомеченных типов, т. е. типов, к которым не применены атрибуты сериализации. Иногда такие типы называют типами POCO (Plain Old CLR Object).</span><span class="sxs-lookup"><span data-stu-id="6ccac-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="6ccac-104">Тип <xref:System.Runtime.Serialization.DataContractSerializer> определяет контракт данных для всех открытых непомеченных типов, имеющих конструктор по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6ccac-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a default constructor.</span></span> <span data-ttu-id="6ccac-105">Контракты данных позволяют передавать структурированные данные в службы и из служб.</span><span class="sxs-lookup"><span data-stu-id="6ccac-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="6ccac-106">Дополнительные сведения о неотмеченных типах см. в разделе [сериализуемые типы](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span><span class="sxs-lookup"><span data-stu-id="6ccac-106">For more information about unmarked types, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="6ccac-107">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), но использует комплексные числа вместо числовых типов-примитивов.</span><span class="sxs-lookup"><span data-stu-id="6ccac-107">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="6ccac-108">Аналогично [базовый контракт данных](../../../../docs/framework/wcf/samples/basic-data-contract.md) выборки, за исключением того, что <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute> атрибуты не используются.</span><span class="sxs-lookup"><span data-stu-id="6ccac-108">It is also similar to the [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="6ccac-109">Клиентом является консольное приложение (EXE), а служба размещается в службах Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="6ccac-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ccac-110">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="6ccac-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6ccac-111">Класс `ComplexNumber` используется классом `ServiceContract`.</span><span class="sxs-lookup"><span data-stu-id="6ccac-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="6ccac-112">У типа `ComplexNumber` нет атрибутов <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, как показано в следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="6ccac-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="6ccac-113">По умолчанию все открытые свойства и поля сериализуются.</span><span class="sxs-lookup"><span data-stu-id="6ccac-113">By default, all public properties and fields are serialized.</span></span>  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6ccac-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="6ccac-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6ccac-115">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6ccac-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="6ccac-116">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6ccac-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="6ccac-117">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6ccac-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ccac-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="6ccac-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6ccac-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="6ccac-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6ccac-120">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="6ccac-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6ccac-121">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="6ccac-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="6ccac-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6ccac-122">See Also</span></span>  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>  
 [<span data-ttu-id="6ccac-123">Сериализуемые типы</span><span class="sxs-lookup"><span data-stu-id="6ccac-123">Serializable Types</span></span>](../../../../docs/framework/wcf/feature-details/serializable-types.md)
