---
title: "Практическое руководство. Настройка подтверждения сигнатуры"
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
- signature confirmation
- WCF, security
ms.assetid: 2424c137-c7c2-4aa9-8d5d-a066e12fefda
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fced2ddd16ae244e2ea3d945082f48ffd23302e6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-set-up-a-signature-confirmation"></a><span data-ttu-id="d4ace-102">Практическое руководство. Настройка подтверждения сигнатуры</span><span class="sxs-lookup"><span data-stu-id="d4ace-102">How to: Set Up a Signature Confirmation</span></span>
<span data-ttu-id="d4ace-103">*Подтверждение подписи* — это механизм для инициатору сообщения убедиться, что полученный ответ был сформирован в ответ на исходное сообщение отправителя.</span><span class="sxs-lookup"><span data-stu-id="d4ace-103">*Signature confirmation* is a mechanism for a message initiator to ensure that a received reply was generated in response to the sender's original message.</span></span> <span data-ttu-id="d4ace-104">Подтверждение подписи определено в спецификации WS-Security 1.1.</span><span class="sxs-lookup"><span data-stu-id="d4ace-104">Signature confirmation is defined in the WS-Security 1.1 specification.</span></span> <span data-ttu-id="d4ace-105">Если конечная точка поддерживает WS-Security 1.0, использовать подтверждение подписи нельзя.</span><span class="sxs-lookup"><span data-stu-id="d4ace-105">If an endpoint supports WS-Security 1.0, you cannot use signature confirmation.</span></span>  
  
 <span data-ttu-id="d4ace-106">В процедурах ниже показано, как включить подтверждение подписи, используя элемент привязки <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="d4ace-106">The following procedures specify how to enable signature confirmation using an <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="d4ace-107">Аналогичным образом можно использовать элемент привязки <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="d4ace-107">You can use the same procedure with a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="d4ace-108">Процедура базируется на основные шаги, описанные в [как: создайте пользовательские привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="d4ace-108">The procedure builds upon the basic steps found in [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-enable-signature-confirmation-in-code"></a><span data-ttu-id="d4ace-109">Включение подтверждения подписи в коде</span><span class="sxs-lookup"><span data-stu-id="d4ace-109">To enable signature confirmation in code</span></span>  
  
1.  <span data-ttu-id="d4ace-110">Создайте экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection>.</span><span class="sxs-lookup"><span data-stu-id="d4ace-110">Create an instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class.</span></span>  
  
2.  <span data-ttu-id="d4ace-111">Создайте экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> класса.</span><span class="sxs-lookup"><span data-stu-id="d4ace-111">Create an instance of the  <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> class.</span></span>  
  
3.  <span data-ttu-id="d4ace-112">Присвойте свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d4ace-112">Set the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> to `true`.</span></span>  
  
4.  <span data-ttu-id="d4ace-113">Добавьте элемент безопасности в коллекцию элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="d4ace-113">Add the security element to the binding collection.</span></span>  
  
5.  <span data-ttu-id="d4ace-114">Создание пользовательской привязки, как указано в [как: Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span><span class="sxs-lookup"><span data-stu-id="d4ace-114">Create a custom binding, as specified in [How to: Create a Custom Binding Using the SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).</span></span>  
  
### <a name="to-enable-signature-confirmation-in-configuration"></a><span data-ttu-id="d4ace-115">Включение подтверждения подписи в конфигурации</span><span class="sxs-lookup"><span data-stu-id="d4ace-115">To enable signature confirmation in configuration</span></span>  
  
1.  <span data-ttu-id="d4ace-116">Добавьте элемент `<customBinding>` в раздел `<bindings>` файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d4ace-116">Add a `<customBinding>` element to the `<bindings>` section of the configuration file.</span></span>  
  
2.  <span data-ttu-id="d4ace-117">Добавьте элемент `<binding>` и присвойте атрибуту имени соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="d4ace-117">Add a `<binding>` element and set the name attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="d4ace-118">Добавьте соответствующий элемент кодирования.</span><span class="sxs-lookup"><span data-stu-id="d4ace-118">Add an appropriate encoding element.</span></span> <span data-ttu-id="d4ace-119">В следующем примере добавляется элемент `<TextMessageEncoding>`.</span><span class="sxs-lookup"><span data-stu-id="d4ace-119">The following example adds a `<TextMessageEncoding>` element.</span></span>  
  
4.  <span data-ttu-id="d4ace-120">Добавьте дочерний элемент `<security>` и присвойте атрибуту `requireSignatureConfirmation` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d4ace-120">Add a `<security>` child element and set the `requireSignatureConfirmation` attribute to `true`.</span></span>  
  
5.  <span data-ttu-id="d4ace-121">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="d4ace-121">Optional.</span></span> <span data-ttu-id="d4ace-122">Включение подтверждения подписи во время начальной загрузки, добавьте [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) дочерний элемент и набор `equireSignatureConfirmation` атрибут `true`.</span><span class="sxs-lookup"><span data-stu-id="d4ace-122">To enable signature confirmation during the bootstrap, add a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element and set the `equireSignatureConfirmation` attribute to `true`.</span></span>  
  
6.  <span data-ttu-id="d4ace-123">Добавьте соответствующий элемент транспорта.</span><span class="sxs-lookup"><span data-stu-id="d4ace-123">Add an appropriate transport element.</span></span> <span data-ttu-id="d4ace-124">В следующем примере добавляется [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):</span><span class="sxs-lookup"><span data-stu-id="d4ace-124">The following example adds an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md):</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SignatureConfirmationBinding">  
          <security requireSignatureConfirmation="true">  
            <secureConversationBootstrap requireSignatureConfirmation="true" />  
              </security>  
           <textMessageEncoding />  
             <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="example"></a><span data-ttu-id="d4ace-125">Пример</span><span class="sxs-lookup"><span data-stu-id="d4ace-125">Example</span></span>  
 <span data-ttu-id="d4ace-126">В приведенном ниже коде создается экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и свойству <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> присваивается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d4ace-126">The following code creates an instance of the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and sets the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.RequireSignatureConfirmation%2A> property to `true`.</span></span> <span data-ttu-id="d4ace-127">Обратите внимание, что в этом примере не используется элемент `<secureConversationBootstrap>`, показанный в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="d4ace-127">Note that this example does not use the `<secureConversationBootstrap>` element shown in the preceding example.</span></span> <span data-ttu-id="d4ace-128">В этом примере демонстрируется подтверждение подписи при использовании маркера Windows (по протоколу Kerberos).</span><span class="sxs-lookup"><span data-stu-id="d4ace-128">This example demonstrates signature confirmation when using a Windows (Kerberos protocol) token.</span></span> <span data-ttu-id="d4ace-129">В данном случае подпись клиента возвращается во всех ответах службы и подтверждается клиентом.</span><span class="sxs-lookup"><span data-stu-id="d4ace-129">In this case, the signature of the client is returned in all responses from the service and is confirmed by the client.</span></span>  
  
 [!code-csharp[c_SignatureConfirmation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_signatureconfirmation/cs/source.cs#1)]
 [!code-vb[c_SignatureConfirmation#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_signatureconfirmation/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d4ace-130">См. также</span><span class="sxs-lookup"><span data-stu-id="d4ace-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>  
 [<span data-ttu-id="d4ace-131">Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="d4ace-131">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="d4ace-132">Как: создание SecurityBindingElement для заданного режима проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="d4ace-132">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
