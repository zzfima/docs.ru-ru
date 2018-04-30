---
title: Возможности безопасности при использовании пользовательских привязок
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
caps.latest.revision: 11
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 31da996feae4e6509bea637bd17b4f538a75c5af
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="security-capabilities-with-custom-bindings"></a><span data-ttu-id="305d7-102">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="305d7-102">Security Capabilities with Custom Bindings</span></span>
<span data-ttu-id="305d7-103">Основные задачи обеспечения безопасности можно выполнить, используя одну из предоставляемых системой привязок.</span><span class="sxs-lookup"><span data-stu-id="305d7-103">You can perform most common security tasks by using one of the system-provided bindings.</span></span> <span data-ttu-id="305d7-104">Однако при необходимости в дополнительных элементах управления можно создать пользовательскую привязку с помощью элемента <xref:System.ServiceModel.Channels.SecurityBindingElement>, следуя объяснениям в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="305d7-104">If you need more control, however, you can create a custom binding with a <xref:System.ServiceModel.Channels.SecurityBindingElement>, as explained in these topics.</span></span> <span data-ttu-id="305d7-105">Дополнительные сведения о пользовательских привязок см. в разделе [пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="305d7-105">For more information about custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="305d7-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="305d7-106">In This Section</span></span>  
 [<span data-ttu-id="305d7-107">Режимы проверки подлинности SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="305d7-107">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 <span data-ttu-id="305d7-108">Содержит описание режимов проверки подлинности, которые возможны для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="305d7-108">Describes the authentication modes that are possible with a custom binding.</span></span>  
  
 [<span data-ttu-id="305d7-109">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="305d7-109">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 <span data-ttu-id="305d7-110">Содержит описание основных шагов, которые необходимо предпринять для создания пользовательской привязки к элементу безопасности.</span><span class="sxs-lookup"><span data-stu-id="305d7-110">Describes the basic steps for creating a custom binding with a security element.</span></span>  
  
 [<span data-ttu-id="305d7-111">Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="305d7-111">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 <span data-ttu-id="305d7-112">Описывается, как создать элемент безопасности для заданного режима проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="305d7-112">Describes how to create a security element for a specified authentication mode.</span></span>  
  
 [<span data-ttu-id="305d7-113">Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="305d7-113">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="305d7-114">Описывается, как отключить безопасные сеансы при создании службы федерации.</span><span class="sxs-lookup"><span data-stu-id="305d7-114">Describes how to disable secure sessions when creating a federation service.</span></span>  
  
 [<span data-ttu-id="305d7-115">Практическое руководство. Включение обнаружения повтора сообщений</span><span class="sxs-lookup"><span data-stu-id="305d7-115">How to: Enable Message Replay Detection</span></span>](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 <span data-ttu-id="305d7-116">Описывается, как определить, когда будет осуществлена атака воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="305d7-116">Describes how to determine when a replay attack occurs.</span></span>  
  
 [<span data-ttu-id="305d7-117">Практическое руководство. Создание подтверждающих учетных данных</span><span class="sxs-lookup"><span data-stu-id="305d7-117">How to: Create a Supporting Credential</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 <span data-ttu-id="305d7-118">Описывается, как предоставить службе подтверждающие учетные данные при необходимости.</span><span class="sxs-lookup"><span data-stu-id="305d7-118">Describes how to supply a supporting credential to a service, if the service requires it.</span></span>  
  
 [<span data-ttu-id="305d7-119">Практическое руководство. Настройка подтверждения сигнатуры</span><span class="sxs-lookup"><span data-stu-id="305d7-119">How to: Set Up a Signature Confirmation</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 <span data-ttu-id="305d7-120">Содержит описание шагов, которые необходимо предпринять для подтверждения подписей при использовании цифровых подписей сообщений.</span><span class="sxs-lookup"><span data-stu-id="305d7-120">Describes the steps to confirm signatures when digitally signing messages.</span></span>  
  
 [<span data-ttu-id="305d7-121">Практическое руководство. Установка максимальной разницы в показаниях часов</span><span class="sxs-lookup"><span data-stu-id="305d7-121">How to: Set a Max Clock Skew</span></span>](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 <span data-ttu-id="305d7-122">Описывается, как настроить максимально допустимую разницу во времени между службой и клиентом.</span><span class="sxs-lookup"><span data-stu-id="305d7-122">Describes how to set the maximum allowed time difference between a service and a client.</span></span>  
  
 [<span data-ttu-id="305d7-123">Практическое руководство. Выключение шифрования цифровых сигнатур</span><span class="sxs-lookup"><span data-stu-id="305d7-123">How to: Disable Encryption of Digital Signatures</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 <span data-ttu-id="305d7-124">Описывается, как отключение шифрования цифровых подписей может увеличить производительность.</span><span class="sxs-lookup"><span data-stu-id="305d7-124">Describes how disabling encryption of digital signatures can have a performance benefit.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="305d7-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="305d7-125">Reference</span></span>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [<span data-ttu-id="305d7-126">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="305d7-126">\<security></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a><span data-ttu-id="305d7-127">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="305d7-127">Related Sections</span></span>  
 [<span data-ttu-id="305d7-128">Основные сведения об уровне защиты</span><span class="sxs-lookup"><span data-stu-id="305d7-128">Understanding Protection Level</span></span>](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [<span data-ttu-id="305d7-129">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="305d7-129">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a><span data-ttu-id="305d7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="305d7-130">See Also</span></span>  
 [<span data-ttu-id="305d7-131">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="305d7-131">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [<span data-ttu-id="305d7-132">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="305d7-132">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="305d7-133">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="305d7-133">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
