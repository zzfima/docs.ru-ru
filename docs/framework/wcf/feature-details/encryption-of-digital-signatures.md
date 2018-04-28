---
title: Шифрование цифровых сигнатур
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- encryption of digital signatures [WCF]
- digital signatures [WCF], encryption
- digital signatures [WCF]
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: aa6abc39159b14eae41e43de5a8976857b1d4c13
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="encryption-of-digital-signatures"></a><span data-ttu-id="32cd1-102">Шифрование цифровых сигнатур</span><span class="sxs-lookup"><span data-stu-id="32cd1-102">Encryption of Digital Signatures</span></span>
<span data-ttu-id="32cd1-103">По умолчанию сообщение подписывается и шифруется, и цифровая подпись шифруется.</span><span class="sxs-lookup"><span data-stu-id="32cd1-103">By default, a message is signed and encrypted, and the signature is digitally encrypted.</span></span> <span data-ttu-id="32cd1-104">Этим процессом можно управлять, создавая пользовательскую привязку с экземпляром элемента <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и затем присваивая свойству `MessageProtectionOrder` каждого класса значение перечисления <xref:System.ServiceModel.Security.MessageProtectionOrder>.</span><span class="sxs-lookup"><span data-stu-id="32cd1-104">You can control this by creating a custom binding with an instance of the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> or the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and then setting the `MessageProtectionOrder` property of either class to a <xref:System.ServiceModel.Security.MessageProtectionOrder> enumeration value.</span></span> <span data-ttu-id="32cd1-105">Значение по умолчанию — <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span><span class="sxs-lookup"><span data-stu-id="32cd1-105">The default is <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span></span> <span data-ttu-id="32cd1-106">Этот процесс занимает на 10 - 40 процентов больше времени, чем просто подписывание и шифрование.</span><span class="sxs-lookup"><span data-stu-id="32cd1-106">This process takes 10 to 40 percent longer than simply signing and encrypting.</span></span> <span data-ttu-id="32cd1-107">Однако в случае отключения шифрования подписи злоумышленник может распознать содержимое сообщения.</span><span class="sxs-lookup"><span data-stu-id="32cd1-107">Disabling encryption of the signature, however, might allow an attacker to guess the contents of the message.</span></span> <span data-ttu-id="32cd1-108">Это обусловлено тем, что элемент подписи содержит хэш-код обычного текста каждой подписанной части сообщения.</span><span class="sxs-lookup"><span data-stu-id="32cd1-108">This is possible because the signature element contains the hash code of the plain text of every signed part in the message.</span></span> <span data-ttu-id="32cd1-109">Например, хотя тело сообщения шифруется по умолчанию, нешифрованная подпись содержит хэш-код тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="32cd1-109">For example, although the message body is encrypted by default, the unencrypted signature contains the hash code of the message body.</span></span> <span data-ttu-id="32cd1-110">Если сообщение короткое, злоумышленник может определить содержимое.</span><span class="sxs-lookup"><span data-stu-id="32cd1-110">If the message is small, an attacker might be able to deduce the contents.</span></span> <span data-ttu-id="32cd1-111">Шифрование подписи уменьшает или исключает эту возможность.</span><span class="sxs-lookup"><span data-stu-id="32cd1-111">Encrypting the signature reduces or eliminates this possibility.</span></span>  
  
 <span data-ttu-id="32cd1-112">Поэтому отключайте шифрование подписи только при малой важности содержимого и существенном повышении производительности в результате такого отключения, например при передаче больших двоичных файлов, не критичных к нарушениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="32cd1-112">Therefore, disable encryption of the signature only when the value of the content is low, and the performance gain will be significant, for example, when sending large binary files that have no security implications.</span></span>  
  
### <a name="to-disable-digital-signing"></a><span data-ttu-id="32cd1-113">Отключение цифровой подписи</span><span class="sxs-lookup"><span data-stu-id="32cd1-113">To disable digital signing</span></span>  
  
1.  <span data-ttu-id="32cd1-114">Создайте таблицу <xref:System.ServiceModel.Channels.CustomBinding>.</span><span class="sxs-lookup"><span data-stu-id="32cd1-114">Create a <xref:System.ServiceModel.Channels.CustomBinding>.</span></span> <span data-ttu-id="32cd1-115">Дополнительные сведения см. в разделе [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="32cd1-115">For more information, see [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
2.  <span data-ttu-id="32cd1-116">Добавьте в коллекцию привязок элемент <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> или <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="32cd1-116">Add either an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> or a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> to the binding collection.</span></span>  
  
3.  <span data-ttu-id="32cd1-117">Присвойте свойству <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> или присвойте свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> значение <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span><span class="sxs-lookup"><span data-stu-id="32cd1-117">Set the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>, or set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="32cd1-118"> создании пользовательских привязок см. в разделе [привязки привязанных к](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="32cd1-118"> creating custom bindings, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="32cd1-119"> Создание пользовательской привязки для конкретного режима проверки подлинности, в разделе [как: создание SecurityBindingElement для режима проверки подлинности указан](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="32cd1-119"> creating a custom binding for a specific authentication mode, see [How to: Create a SecurityBindingElement for a Specified Authentication Mode](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32cd1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="32cd1-120">See Also</span></span>  
 <xref:System.ServiceModel.Security.MessageProtectionOrder>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 [<span data-ttu-id="32cd1-121">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="32cd1-121">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="32cd1-122">Создание пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="32cd1-122">Creating User-Defined Bindings</span></span>](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)  
 [<span data-ttu-id="32cd1-123">Практическое руководство. Создание SecurityBindingElement для заданного режима проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="32cd1-123">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
