---
title: Практическое руководство. Использование моникера службы с контрактами обмена метаданными
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 367cbd4a2bfbde3d4ab0a74eeeaf5d5f5662ec27
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319837"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="56d60-102">Практическое руководство. Использование моникера службы с контрактами обмена метаданными</span><span class="sxs-lookup"><span data-stu-id="56d60-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="56d60-103">После разработки некоторые новые службы WCF, вы решите, что вы хотите иметь возможность вызывать эти службы из файла скрипта или приложения Visual Basic 6.0.</span><span class="sxs-lookup"><span data-stu-id="56d60-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="56d60-104">Один из методов можно создать сборку клиента WCF, Зарегистрируйте сборку с помощью COM, установите сборку в глобальный кэш СБОРОК и затем ссылаться на типы COM из кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="56d60-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="56d60-105">При распространении приложения, необходимо распространить клиента WCF к сборке.</span><span class="sxs-lookup"><span data-stu-id="56d60-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="56d60-106">Затем пользователь должен будет зарегистрировать клиентскую сборку WCF с помощью COM и разместить ее в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="56d60-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="56d60-107">COM-взаимодействия WCF также позволяет сделать вызовы той же службы, не полагаясь на клиентскую сборку WCF.</span><span class="sxs-lookup"><span data-stu-id="56d60-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="56d60-108">Моникера WCF позволяет вызывать любую службу WCF из любого COM-совместимого языка (Visual Basic, VBScript, Visual Basic for Applications (VBA) и т. д.), указав конечную точку метаданных exchange (Mex) URI, моникер служб использует для извлечения типа сведения о службе.</span><span class="sxs-lookup"><span data-stu-id="56d60-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="56d60-109">В этом разделе описывается, как вызывать пример Приступая к работе с WCF, с помощью моникера WCF, указывающего конечную точку обмена метаданными.</span><span class="sxs-lookup"><span data-stu-id="56d60-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56d60-110">Фактически никогда не создаются типы, определенные в сборке клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="56d60-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="56d60-111">Сборка используется только для метаданных.</span><span class="sxs-lookup"><span data-stu-id="56d60-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="56d60-112">Использование моникера службы с адресом обмена метаданными (Mex)</span><span class="sxs-lookup"><span data-stu-id="56d60-112">Using the service moniker with a Mex address</span></span>  
  
1. <span data-ttu-id="56d60-113">Построение образца Приступая к работе и перейдите по URL-адресу с помощью Internet Explorer (http://localhost/ServiceModelSamples/Service.svc) чтобы убедиться, что служба работает.</span><span class="sxs-lookup"><span data-stu-id="56d60-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2. <span data-ttu-id="56d60-114">Создайте скрипт Visual Basic или приложение Visual Basic, содержащее следующий код:</span><span class="sxs-lookup"><span data-stu-id="56d60-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="56d60-115">Запустите приложение или скрипт Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="56d60-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56d60-116">Вызываемая служба должна экспонировать конечную точку обмена метаданными (Mex) в моникер, чтобы прочитать метаданные из службы.</span><span class="sxs-lookup"><span data-stu-id="56d60-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="56d60-117">Дополнительные сведения см. в разделе [Как Публикация метаданных для службы с помощью файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="56d60-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56d60-118">Если моникер сформирован неправильно или служба недоступна, при вызове `GetObject` будет возвращена ошибка "Синтаксическая ошибка".</span><span class="sxs-lookup"><span data-stu-id="56d60-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="56d60-119">При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.</span><span class="sxs-lookup"><span data-stu-id="56d60-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56d60-120">См. также</span><span class="sxs-lookup"><span data-stu-id="56d60-120">See also</span></span>

- [<span data-ttu-id="56d60-121">Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации</span><span class="sxs-lookup"><span data-stu-id="56d60-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="56d60-122">Практическое руководство. Использование моникера службы с контрактами WSDL</span><span class="sxs-lookup"><span data-stu-id="56d60-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
