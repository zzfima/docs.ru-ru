---
title: Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
ms.openlocfilehash: e35df9a5dacc5f281af48cec292a09b291312119
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124518"
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="c509c-102">Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="c509c-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
<span data-ttu-id="c509c-103">Windows Communication Foundation (WCF) предоставляет несколько режимов, по которым клиенты и службы проверяют подлинность друг друга.</span><span class="sxs-lookup"><span data-stu-id="c509c-103">Windows Communication Foundation (WCF) provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="c509c-104">Для этих режимов проверки подлинности можно создать привязки безопасности с помощью статических методов класса <xref:System.ServiceModel.Channels.SecurityBindingElement> или с помощью конфигурации, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="c509c-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 <span data-ttu-id="c509c-105">Дополнительные сведения о 18 режимов проверки подлинности, см. в разделе [режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="c509c-105">For more information about the 18 authentication modes, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c509c-106">Пример</span><span class="sxs-lookup"><span data-stu-id="c509c-106">Example</span></span>  
 <span data-ttu-id="c509c-107">В следующем примере кода показаны методы создания привязок для различных методов проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="c509c-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c509c-108">После создания объекта <xref:System.ServiceModel.Channels.SecurityBindingElement> некоторые свойства являются неизменяемыми, такие как <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> и <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="c509c-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="c509c-109">Вызов `set` для этих свойств не изменяет их.</span><span class="sxs-lookup"><span data-stu-id="c509c-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c509c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c509c-110">See also</span></span>

- [<span data-ttu-id="c509c-111">Режимы проверки подлинности SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c509c-111">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)
- [<span data-ttu-id="c509c-112">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="c509c-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
