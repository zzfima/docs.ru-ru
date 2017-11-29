---
title: "Практическое руководство. Использование моникера службы с контрактами обмена метаданными"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ed6ce9b87a5e2d8945a57110c02cce8024439f14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="91d5e-102">Практическое руководство. Использование моникера службы с контрактами обмена метаданными</span><span class="sxs-lookup"><span data-stu-id="91d5e-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="91d5e-103">Разработав несколько новых служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], вы, возможно, решите предусмотреть возможность вызова данных служб из скрипта или приложения на Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="91d5e-103">After developing some new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="91d5e-104">Один способ - это создание клиентской сборки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], регистрация сборки с помощью COM, установка сборки в глобальном кэше сборок, а затем ссылка на COM-типы из кода на Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="91d5e-104">One method would be to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="91d5e-105">При распространении приложения также потребуется распространять клиентскую сборку [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91d5e-105">When you distribute the application, you will have to distribute the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client assembly as well.</span></span> <span data-ttu-id="91d5e-106">Затем пользователь должен будет зарегистрировать клиентскую сборку WCF с помощью COM и разместить ее в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="91d5e-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="91d5e-107"> COM Interop также позволяет выполнять вызовы той же службы без клиентской сборки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="91d5e-107"> COM Interop also allows you to make the same service calls without relying on a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly.</span></span> <span data-ttu-id="91d5e-108">Моникер [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет вызывать любую службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] из любого COM-совместимого языка (Visual Basic, VBScript, Visual Basic for Applications (VBA) и т. п.) путем указания универсального кода ресурса (URI) конечной точки обмена метаданными (Mex), используемого моникером для извлечения типовой информации о службе.</span><span class="sxs-lookup"><span data-stu-id="91d5e-108">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker allows you to call any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="91d5e-109">В настоящем разделе описывается, как вызывать пример начала работы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью моникера [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], указывающего конечную точку обмена метаданными (Mex).</span><span class="sxs-lookup"><span data-stu-id="91d5e-109">This topic describes how to call the Getting Started [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91d5e-110">Типы, определенные клиентской сборкой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], фактически не используются для создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="91d5e-110">The types defined by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly are never actually instantiated.</span></span> <span data-ttu-id="91d5e-111">Сборка используется только для метаданных.</span><span class="sxs-lookup"><span data-stu-id="91d5e-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="91d5e-112">Использование моникера службы с адресом обмена метаданными (Mex)</span><span class="sxs-lookup"><span data-stu-id="91d5e-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="91d5e-113">Создайте пример начала работы и с помощью Internet Explorer перейдите по его URL-адресу (http://localhost/ServiceModelSamples/Service.svc), чтобы удостовериться в работоспособности службы.</span><span class="sxs-lookup"><span data-stu-id="91d5e-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="91d5e-114">Создайте скрипт Visual Basic или приложение Visual Basic, содержащее следующий код:</span><span class="sxs-lookup"><span data-stu-id="91d5e-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="91d5e-115">Запустите приложение или скрипт Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="91d5e-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91d5e-116">Вызываемая служба должна экспонировать конечную точку обмена метаданными (Mex) в моникер, чтобы прочитать метаданные из службы.</span><span class="sxs-lookup"><span data-stu-id="91d5e-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="91d5e-117">Дополнительные сведения см. в разделе [как: публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="91d5e-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91d5e-118">Если моникер сформирован неправильно или служба недоступна, при вызове `GetObject` будет возвращена ошибка "Синтаксическая ошибка".</span><span class="sxs-lookup"><span data-stu-id="91d5e-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="91d5e-119">При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.</span><span class="sxs-lookup"><span data-stu-id="91d5e-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d5e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="91d5e-120">See Also</span></span>  
 [<span data-ttu-id="91d5e-121">Как: использование моникера службы Windows Communication Foundation без регистрации</span><span class="sxs-lookup"><span data-stu-id="91d5e-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [<span data-ttu-id="91d5e-122">Как: использование моникера службы с контрактами WSDL</span><span class="sxs-lookup"><span data-stu-id="91d5e-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
