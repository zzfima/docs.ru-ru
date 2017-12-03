---
title: "Практическое руководство. Изменение привязки, предоставляемой системой"
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
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c46886879d19d612827b94821e0105c68c437c56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-customize-a-system-provided-binding"></a><span data-ttu-id="90c28-102">Практическое руководство. Изменение привязки, предоставляемой системой</span><span class="sxs-lookup"><span data-stu-id="90c28-102">How to: Customize a System-Provided Binding</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="90c28-103"> содержит несколько привязок, предоставляемых системой, которые позволяют настраивать некоторые свойства базовых элементов привязки, но не все свойства.</span><span class="sxs-lookup"><span data-stu-id="90c28-103"> includes several system-provided bindings that allow you to configure some of the properties of the underlying binding elements, but not all of the properties.</span></span> <span data-ttu-id="90c28-104">В данном разделе показано, как задать свойства в элементах привязки, чтобы создать пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="90c28-104">This topic demonstrates how to set properties on the binding elements to create a custom binding.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="90c28-105">как непосредственно создать и настроить элементы привязки без использования системных привязок см. в разделе [пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="90c28-105"> how to directly create and configure binding elements without using the system-provided bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="90c28-106">Создание и расширение пользовательских привязок. в разделе [расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="90c28-106"> creating and extending custom bindings, see [Extending Bindings](../../../../docs/framework/wcf/extending/extending-bindings.md).</span></span>  
  
 <span data-ttu-id="90c28-107">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] все привязки состоят из *элементов привязки*.</span><span class="sxs-lookup"><span data-stu-id="90c28-107">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] all bindings are made up of *binding elements*.</span></span> <span data-ttu-id="90c28-108">Каждый элемент привязки наследуется от класса <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="90c28-108">Each binding element derives from the <xref:System.ServiceModel.Channels.BindingElement> class.</span></span> <span data-ttu-id="90c28-109">Привязки, предоставляемые системой, такие как <xref:System.ServiceModel.BasicHttpBinding>, создают и настраивают собственные элементы привязки.</span><span class="sxs-lookup"><span data-stu-id="90c28-109">System-provided bindings such as <xref:System.ServiceModel.BasicHttpBinding> create and configure their own binding elements.</span></span> <span data-ttu-id="90c28-110">В данном разделе показано, как получить доступ и изменить свойства этих элементов привязки, которые не предоставляются непосредственно в привязке, в частности, класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="90c28-110">This topic shows you how to access and change the properties of these binding elements, which are not directly exposed on the binding; specifically, the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="90c28-111">Отдельные элементы привязки содержатся в коллекции, представленной классом <xref:System.ServiceModel.Channels.BindingElementCollection>, и добавляются в следующем порядке: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding и Transport.</span><span class="sxs-lookup"><span data-stu-id="90c28-111">The individual binding elements are contained in a collection represented by the <xref:System.ServiceModel.Channels.BindingElementCollection> class and are added in this order: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding, and Transport.</span></span> <span data-ttu-id="90c28-112">Обратите внимание, что все перечисленные элементы привязки являются обязательными для каждой привязки.</span><span class="sxs-lookup"><span data-stu-id="90c28-112">Note that not all the binding elements listed are required in every binding.</span></span> <span data-ttu-id="90c28-113">Пользовательские элементы привязки также могут отображаться в коллекции элементов привязки и должны отображаться в указанном выше порядке.</span><span class="sxs-lookup"><span data-stu-id="90c28-113">User-defined binding elements can also appear in this binding element collection and must appear in the same order as previously described.</span></span> <span data-ttu-id="90c28-114">Например, пользовательский транспорт должен быть последним элементом в коллекции элементов привязки.</span><span class="sxs-lookup"><span data-stu-id="90c28-114">For example, a user-defined transport must be the last element of the binding element collection.</span></span>  
  
 <span data-ttu-id="90c28-115">Класс <xref:System.ServiceModel.BasicHttpBinding> содержит три элемента привязки.</span><span class="sxs-lookup"><span data-stu-id="90c28-115">The <xref:System.ServiceModel.BasicHttpBinding> class contains three binding elements:</span></span>  
  
1.  <span data-ttu-id="90c28-116">Необязательный элемент привязки безопасности: класс <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>, используемый с транспортом HTTP (безопасность на уровне сообщений), или класс <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, используемый при предоставлении безопасности на уровне транспорта, при этом используется транспорт HTTPS.</span><span class="sxs-lookup"><span data-stu-id="90c28-116">An optional security binding element, either the <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> class used with the HTTP transport (message level security) or the <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> class, which is used when the transport layer provides security, in which case the HTTPS transport is used.</span></span>  
  
2.  <span data-ttu-id="90c28-117">Обязательный элемент привязки кодировщика сообщений: элемент <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> или элемент <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="90c28-117">A required message encoder binding element, either <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> or <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.</span></span>  
  
3.  <span data-ttu-id="90c28-118">Обязательный элемент привязки транспорта: элемент <xref:System.ServiceModel.Channels.HttpTransportBindingElement> или элемент <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="90c28-118">A required transport binding element, either <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, or <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span></span>  
  
 <span data-ttu-id="90c28-119">В этом примере создается экземпляр привязки, *пользовательской привязки* от него, проверяются элементы привязки из пользовательской привязки, и при обнаружении элемента привязки HTTP его `KeepAliveEnabled` свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="90c28-119">In this example we create an instance of the binding, generate a *custom binding* from it, examine the binding elements in the custom binding, and when we find the HTTP binding element, we set its `KeepAliveEnabled` property to `false`.</span></span> <span data-ttu-id="90c28-120">Свойство `KeepAliveEnabled` не представлено напрямую в привязке `BasicHttpBinding`, поэтому необходимо создать пользовательскую привязку, чтобы перейти вниз к элементу привязки и присвоить этому свойству значение.</span><span class="sxs-lookup"><span data-stu-id="90c28-120">The `KeepAliveEnabled` property is not exposed directly on the `BasicHttpBinding`, so we must create a custom binding to navigate down to the binding element and set this property.</span></span>  
  
### <a name="to-modify-a-system-provided-binding"></a><span data-ttu-id="90c28-121">Изменение привязки, предоставляемой системой</span><span class="sxs-lookup"><span data-stu-id="90c28-121">To modify a system-provided binding</span></span>  
  
1.  <span data-ttu-id="90c28-122">Создайте экземпляр класса <xref:System.ServiceModel.BasicHttpBinding> и установите для него режим безопасности на уровне сообщений.</span><span class="sxs-lookup"><span data-stu-id="90c28-122">Create an instance of the <xref:System.ServiceModel.BasicHttpBinding> class and set its security mode to message-level.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  <span data-ttu-id="90c28-123">Создайте пользовательскую привязку из привязки и создайте класс <xref:System.ServiceModel.Channels.BindingElementCollection> из одного из свойств пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="90c28-123">Create a custom binding from the binding and create a <xref:System.ServiceModel.Channels.BindingElementCollection> class from one of the custom binding's properties.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  <span data-ttu-id="90c28-124">Выполните цикл по классу <xref:System.ServiceModel.Channels.BindingElementCollection> и при нахождении класса <xref:System.ServiceModel.Channels.HttpTransportBindingElement> присвойте его свойству <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="90c28-124">Loop through the <xref:System.ServiceModel.Channels.BindingElementCollection> class, and when you find the <xref:System.ServiceModel.Channels.HttpTransportBindingElement> class, set its <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property to `false`.</span></span>  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="90c28-125">См. также</span><span class="sxs-lookup"><span data-stu-id="90c28-125">See Also</span></span>  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="90c28-126">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="90c28-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)
