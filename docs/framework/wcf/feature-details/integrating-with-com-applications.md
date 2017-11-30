---
title: "Интеграция с приложениями COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0e625beaf20f6445099d8fb15cb175d3d71a860
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="integrating-with-com-applications"></a><span data-ttu-id="c7219-102">Интеграция с приложениями COM</span><span class="sxs-lookup"><span data-stu-id="c7219-102">Integrating with COM Applications</span></span>
<span data-ttu-id="c7219-103">Службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно объединить непосредственно с существующим кодом с помощью моникера службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7219-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services can be integrated directly into your existing code by using the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker.</span></span> <span data-ttu-id="c7219-104">Моникер служб можно использовать в широком наборе сред разработки на базе модели COM, например в Office VBA, Visual Basic 6.0 и Visual C++ 6.0.</span><span class="sxs-lookup"><span data-stu-id="c7219-104">The service moniker can be used from a wide range of COM-based development environments, such as Office VBA, Visual Basic 6.0, or Visual C++ 6.0.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7219-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="c7219-105">In This Section</span></span>  
 [<span data-ttu-id="c7219-106">Интеграция с Общие сведения о приложениях COM</span><span class="sxs-lookup"><span data-stu-id="c7219-106">Integrating with COM Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 <span data-ttu-id="c7219-107">Предоставляет общие сведения об основных компонентах процесса объединения.</span><span class="sxs-lookup"><span data-stu-id="c7219-107">Gives an overview of the major parts of the integration process.</span></span>  
  
 [<span data-ttu-id="c7219-108">Как: регистрация и настройка моникера службы</span><span class="sxs-lookup"><span data-stu-id="c7219-108">How to: Register and Configure a Service Moniker</span></span>](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 <span data-ttu-id="c7219-109">Чтобы начать использовать моникер службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в рамках приложения COM, зарегистрируйте необходимые типы с атрибутами с помощью COM и настройте приложение COM и моникер в соответствии с необходимой конфигурацией привязки.</span><span class="sxs-lookup"><span data-stu-id="c7219-109">To use the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker within a COM application, register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
 [<span data-ttu-id="c7219-110">Как: использование моникера службы Windows Communication Foundation без регистрации</span><span class="sxs-lookup"><span data-stu-id="c7219-110">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 <span data-ttu-id="c7219-111">Содержит объяснения, как получить определение контракта в форме документа языка описания веб-служб (WSDL) или из конечной точки WS-MetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="c7219-111">Explains how to obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document or from a WS-MetadataExchange endpoint.</span></span>  
  
 [<span data-ttu-id="c7219-112">Как: использование моникера службы с контрактами WSDL</span><span class="sxs-lookup"><span data-stu-id="c7219-112">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 <span data-ttu-id="c7219-113">Содержит описание, как вызвать пример [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью моникера WSDL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c7219-113">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WSDL moniker.</span></span>  
  
 [<span data-ttu-id="c7219-114">Как: использование моникера службы с контрактами обмена метаданными</span><span class="sxs-lookup"><span data-stu-id="c7219-114">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 <span data-ttu-id="c7219-115">Содержит описание, как вызывать пример [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью моникера [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], указывающего конечную точку обмена метаданными (Mex).</span><span class="sxs-lookup"><span data-stu-id="c7219-115">Describes how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
 [<span data-ttu-id="c7219-116">Как: укажите учетные данные безопасности канала</span><span class="sxs-lookup"><span data-stu-id="c7219-116">How to: Specify Channel Security Credentials</span></span>](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 <span data-ttu-id="c7219-117">Моникер службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает интерфейс `IChannelCredentials`, который обеспечивает ряд альтернативных методов указания учетных данных каналов.</span><span class="sxs-lookup"><span data-stu-id="c7219-117">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service moniker supports the `IChannelCredentials` interface that allows a range of alternate methods for specifying channel credentials.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c7219-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="c7219-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a><span data-ttu-id="c7219-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c7219-119">See Also</span></span>  
 [<span data-ttu-id="c7219-120">Интеграция с приложениями COM +</span><span class="sxs-lookup"><span data-stu-id="c7219-120">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
