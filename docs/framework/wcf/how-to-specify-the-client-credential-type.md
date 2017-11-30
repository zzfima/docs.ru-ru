---
title: "Практическое руководство. Указание типа учетных данных клиента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 35c3b5ee429f7c9337fa3c3e3eb0d0476e3f56d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="1c8ec-102">Практическое руководство. Указание типа учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="1c8ec-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="1c8ec-103">После установки режима безопасности (на уровне транспорта или сообщений) можно установить тип учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="1c8ec-104">Это свойство определяет тип учетных данных, которые клиент должен предоставить службе для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="1c8ec-105">режим безопасности (необходимым этапом перед установкой типа учетных данных клиента), см. параметр [как: режим безопасности](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="1c8ec-105"> setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="1c8ec-106">Установка типа учетных данных клиента в коде</span><span class="sxs-lookup"><span data-stu-id="1c8ec-106">To set the client credential type in code</span></span>  
  
1.  <span data-ttu-id="1c8ec-107">Создайте экземпляр привязки, который будет использовать служба.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="1c8ec-108">В этом примере используется привязка <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2.  <span data-ttu-id="1c8ec-109">Присвойте свойству <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="1c8ec-110">В этом примере используется режим Message.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-110">This example uses the Message mode.</span></span>  
  
3.  <span data-ttu-id="1c8ec-111">Присвойте свойству <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="1c8ec-112">В этом примере используется проверка подлинности Windows (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span><span class="sxs-lookup"><span data-stu-id="1c8ec-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="1c8ec-113">Установка типа учетных данных клиента в файле конфигурации</span><span class="sxs-lookup"><span data-stu-id="1c8ec-113">To set the client credential type in configuration</span></span>  
  
1.  <span data-ttu-id="1c8ec-114">Добавить [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2.  <span data-ttu-id="1c8ec-115">В качестве дочернего элемента, добавить [ \<привязки >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3.  <span data-ttu-id="1c8ec-116">Добавьте соответствующую привязку.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-116">Add an appropriate binding.</span></span> <span data-ttu-id="1c8ec-117">В этом примере используется [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4.  <span data-ttu-id="1c8ec-118">Добавить [ \<привязки >](../../../docs/framework/misc/binding.md) и присвойте `name` соответствующее значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="1c8ec-119">В этом примере используется имя "SecureBinding".</span><span class="sxs-lookup"><span data-stu-id="1c8ec-119">This example uses the name "SecureBinding".</span></span>  
  
5.  <span data-ttu-id="1c8ec-120">Добавьте привязку `<security>`.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-120">Add a `<security>` binding.</span></span> <span data-ttu-id="1c8ec-121">Присвойте атрибуту `mode` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="1c8ec-122">В данном примере используется значение `"Message"`.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-122">This example sets it to `"Message"`.</span></span>  
  
6.  <span data-ttu-id="1c8ec-123">Добавьте элемент `<message>` или `<transport>` в зависимости от режима безопасности.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="1c8ec-124">Присвойте атрибуту `clientCredentialType` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="1c8ec-125">В этом примере используется `"Windows"`.</span><span class="sxs-lookup"><span data-stu-id="1c8ec-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1c8ec-126">См. также</span><span class="sxs-lookup"><span data-stu-id="1c8ec-126">See Also</span></span>  
 [<span data-ttu-id="1c8ec-127">Защита служб</span><span class="sxs-lookup"><span data-stu-id="1c8ec-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="1c8ec-128">Практическое руководство. Задание режима безопасности</span><span class="sxs-lookup"><span data-stu-id="1c8ec-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
