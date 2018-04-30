---
title: Практическое руководства. Создание SecurityBindingElement для заданного режима проверки подлинности
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: 9
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 423ec48aac29c0aba2b4f4dda1b68f3c1979c5e4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="61628-102">Практическое руководства. Создание SecurityBindingElement для заданного режима проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="61628-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
<span data-ttu-id="61628-103">В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] имеется несколько режимов, с помощью которых клиенты и службы проверяют подлинность друг друга.</span><span class="sxs-lookup"><span data-stu-id="61628-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="61628-104">Для этих режимов проверки подлинности можно создать привязки безопасности с помощью статических методов класса <xref:System.ServiceModel.Channels.SecurityBindingElement> или с помощью конфигурации, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="61628-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="61628-105">Дополнительные сведения о режимах проверки подлинности 18 см. в разделе [режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="61628-105">For more information about the 18 authentication modes, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61628-106">Пример</span><span class="sxs-lookup"><span data-stu-id="61628-106">Example</span></span>  
 <span data-ttu-id="61628-107">В следующем примере кода показаны методы создания привязок для различных методов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="61628-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61628-108">После создания объекта <xref:System.ServiceModel.Channels.SecurityBindingElement> некоторые свойства являются неизменяемыми, такие как <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> и <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="61628-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="61628-109">Вызов `set` для этих свойств не изменяет их.</span><span class="sxs-lookup"><span data-stu-id="61628-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="61628-110">См. также</span><span class="sxs-lookup"><span data-stu-id="61628-110">See Also</span></span>  
 [<span data-ttu-id="61628-111">Режимы проверки подлинности SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="61628-111">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 [<span data-ttu-id="61628-112">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="61628-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
