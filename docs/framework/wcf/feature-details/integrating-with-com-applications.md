---
title: Интеграция с приложениями COM
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: 292892ef572bd63fff055aeed88073573fadb934
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="f3ac8-102">Интеграция с приложениями COM</span><span class="sxs-lookup"><span data-stu-id="f3ac8-102">Integrating with COM Applications</span></span>
<span data-ttu-id="f3ac8-103">Службы Windows Communication Foundation (WCF) могут интегрироваться прямо в существующий код с помощью моникера службы WCF.</span><span class="sxs-lookup"><span data-stu-id="f3ac8-103">Windows Communication Foundation (WCF) services can be integrated directly into your existing code by using the WCF service moniker.</span></span> <span data-ttu-id="f3ac8-104">Моникер служб можно использовать в широком наборе сред разработки на базе модели COM, например в Office VBA, Visual Basic 6.0 и Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="f3ac8-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f3ac8-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f3ac8-105">In This Section</span></span>  
 [<span data-ttu-id="f3ac8-106">Общие сведения об интеграции с приложениями COM</span><span class="sxs-lookup"><span data-stu-id="f3ac8-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="f3ac8-107">Предоставляет общие сведения об основных компонентах процесса объединения.</span><span class="sxs-lookup"><span data-stu-id="f3ac8-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="f3ac8-108">Практическое руководство. Регистрация и настройка моникера службы</span><span class="sxs-lookup"><span data-stu-id="f3ac8-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="f3ac8-109">Чтобы использовать моникер службы WCF в приложении COM, зарегистрируйте необходимые типы с атрибутами с помощью COM и настроить приложение COM и моникер в соответствии с необходимой конфигурацией привязки.</span><span class="sxs-lookup"><span data-stu-id="f3ac8-109">To use the WCF service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="f3ac8-110">Практическое руководство. Использование моникера службы Windows Communication Foundation без регистрации</span><span class="sxs-lookup"><span data-stu-id="f3ac8-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="f3ac8-111">Содержит объяснения, как получить определение контракта в форме документа языка описания веб-служб (WSDL) или из конечной точки WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="f3ac8-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="f3ac8-112">Практическое руководство. Использование моникера службы с контрактами WSDL</span><span class="sxs-lookup"><span data-stu-id="f3ac8-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="f3ac8-113">Описывает, как вызвать образец WCF, с помощью моникера WSDL для службы WCF.</span><span class="sxs-lookup"><span data-stu-id="f3ac8-113">Describes how to call a WCF sample using a WCF WSDL moniker.</span></span>  
  
 [<span data-ttu-id="f3ac8-114">Практическое руководство. Использование моникера службы с контрактами обмена метаданными</span><span class="sxs-lookup"><span data-stu-id="f3ac8-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="f3ac8-115">Описывает, как вызвать образец WCF, с помощью моникера WCF, указывающего конечную точку обмена метаданными.</span><span class="sxs-lookup"><span data-stu-id="f3ac8-115">Describes how to call a WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="f3ac8-116">Практическое руководство. Задание учетных данных безопасности канала</span><span class="sxs-lookup"><span data-stu-id="f3ac8-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="f3ac8-117">Моникер службы WCF поддерживает `IChannelCredentials` интерфейс, который обеспечивает ряд альтернативных методов указания учетных данных канала.</span><span class="sxs-lookup"><span data-stu-id="f3ac8-117">The WCF service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f3ac8-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f3ac8-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="f3ac8-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f3ac8-119">See Also</span></span>  
 [<span data-ttu-id="f3ac8-120">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="f3ac8-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
