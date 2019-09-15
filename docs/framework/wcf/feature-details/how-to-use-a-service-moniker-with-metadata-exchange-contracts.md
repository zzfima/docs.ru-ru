---
title: Практическое руководство. Использование моникера службы с контрактами обмена метаданными
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: e114bc2c046ba7145a91121ce23c82912680a048
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2019
ms.locfileid: "70968965"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="350ed-102">Практическое руководство. Использование моникера службы с контрактами обмена метаданными</span><span class="sxs-lookup"><span data-stu-id="350ed-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="350ed-103">После разработки некоторых новых служб WCF вы можете решить, что они могут вызывать эти службы из сценария или приложения Visual Basic 6,0.</span><span class="sxs-lookup"><span data-stu-id="350ed-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="350ed-104">Одним из способов является создание клиентской сборки WCF, регистрация сборки в COM, установка сборки в GAC, а также ссылки на типы COM из кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="350ed-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="350ed-105">При распространении приложения потребуется также распространять клиентскую сборку WCF.</span><span class="sxs-lookup"><span data-stu-id="350ed-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="350ed-106">Затем пользователь должен будет зарегистрировать клиентскую сборку WCF с помощью COM и разместить ее в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="350ed-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="350ed-107">COM-взаимодействие WCF также позволяет выполнять одни и те же вызовы служб, не полагаясь на клиентскую сборку WCF.</span><span class="sxs-lookup"><span data-stu-id="350ed-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="350ed-108">Моникер WCF позволяет вызывать любую службу WCF на любом языке, совместимом с COM (Visual Basic, VBScript, Visual Basic для приложений (VBA) и т. д.), указывая URI конечной точки обмена метаданными (MEX), который моникер службы использует для извлечения типа. сведения о службе.</span><span class="sxs-lookup"><span data-stu-id="350ed-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="350ed-109">В этом разделе описывается, как вызвать пример начало работы WCF с помощью моникера WCF, который указывает конечную точку обмена метаданными.</span><span class="sxs-lookup"><span data-stu-id="350ed-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="350ed-110">Типы, определенные клиентской сборкой WCF, никогда не создаются.</span><span class="sxs-lookup"><span data-stu-id="350ed-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="350ed-111">Сборка используется только для метаданных.</span><span class="sxs-lookup"><span data-stu-id="350ed-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="350ed-112">Использование моникера службы с адресом обмена метаданными (Mex)</span><span class="sxs-lookup"><span data-stu-id="350ed-112">Using the service moniker with a Mex address</span></span>  
  
1. <span data-ttu-id="350ed-113">Создайте пример начало работы и используйте Internet Explorer, чтобы перейти к своему URL- http://localhost/ServiceModelSamples/Service.svc) адресу (чтобы убедиться, что служба работает).</span><span class="sxs-lookup"><span data-stu-id="350ed-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2. <span data-ttu-id="350ed-114">Создайте скрипт Visual Basic или приложение Visual Basic, содержащее следующий код:</span><span class="sxs-lookup"><span data-stu-id="350ed-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="350ed-115">Запустите приложение или скрипт Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="350ed-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="350ed-116">Вызываемая служба должна экспонировать конечную точку обмена метаданными (Mex) в моникер, чтобы прочитать метаданные из службы.</span><span class="sxs-lookup"><span data-stu-id="350ed-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="350ed-117">Дополнительные сведения см. в разделе [Практическое руководство. Публикация метаданных для службы с помощью файла](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)конфигурации.</span><span class="sxs-lookup"><span data-stu-id="350ed-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="350ed-118">Если моникер сформирован неправильно или служба недоступна, при вызове `GetObject` будет возвращена ошибка "Синтаксическая ошибка".</span><span class="sxs-lookup"><span data-stu-id="350ed-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="350ed-119">При получении этой ошибки убедитесь, что используется правильный моникер, а служба доступна.</span><span class="sxs-lookup"><span data-stu-id="350ed-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350ed-120">См. также</span><span class="sxs-lookup"><span data-stu-id="350ed-120">See also</span></span>

- [<span data-ttu-id="350ed-121">Практическое руководство. Использовать моникер службы Windows Communication Foundation без регистрации</span><span class="sxs-lookup"><span data-stu-id="350ed-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="350ed-122">Практическое руководство. Использование моникера службы с контрактами WSDL</span><span class="sxs-lookup"><span data-stu-id="350ed-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
