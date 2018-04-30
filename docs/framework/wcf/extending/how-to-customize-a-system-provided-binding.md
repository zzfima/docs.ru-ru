---
title: Практическое руководство. Изменение привязки, предоставляемой системой
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
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d70a4c4234047e7410ae4f631e48595a0859f37
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-customize-a-system-provided-binding"></a>Практическое руководство. Изменение привязки, предоставляемой системой
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] содержит несколько привязок, предоставляемых системой, которые позволяют настраивать некоторые свойства базовых элементов привязки, но не все свойства. В данном разделе показано, как задать свойства в элементах привязки, чтобы создать пользовательскую привязку.  
  
 Дополнительные сведения о том, как непосредственно создать и настроить элементы привязки без использования системных привязок см. в разделе [пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Дополнительные сведения о создании и расширении пользовательских привязок см. в разделе [расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] все привязки состоят из *элементов привязки*. Каждый элемент привязки наследуется от класса <xref:System.ServiceModel.Channels.BindingElement>. Привязки, предоставляемые системой, такие как <xref:System.ServiceModel.BasicHttpBinding>, создают и настраивают собственные элементы привязки. В данном разделе показано, как получить доступ и изменить свойства этих элементов привязки, которые не предоставляются непосредственно в привязке, в частности, класс <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Отдельные элементы привязки содержатся в коллекции, представленной классом <xref:System.ServiceModel.Channels.BindingElementCollection>, и добавляются в следующем порядке: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding и Transport. Обратите внимание, что все перечисленные элементы привязки являются обязательными для каждой привязки. Пользовательские элементы привязки также могут отображаться в коллекции элементов привязки и должны отображаться в указанном выше порядке. Например, пользовательский транспорт должен быть последним элементом в коллекции элементов привязки.  
  
 Класс <xref:System.ServiceModel.BasicHttpBinding> содержит три элемента привязки.  
  
1.  Необязательный элемент привязки безопасности: класс <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>, используемый с транспортом HTTP (безопасность на уровне сообщений), или класс <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, используемый при предоставлении безопасности на уровне транспорта, при этом используется транспорт HTTPS.  
  
2.  Обязательный элемент привязки кодировщика сообщений: элемент <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> или элемент <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>.  
  
3.  Обязательный элемент привязки транспорта: элемент <xref:System.ServiceModel.Channels.HttpTransportBindingElement> или элемент <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.  
  
 В этом примере создается экземпляр привязки, *пользовательской привязки* от него, проверяются элементы привязки из пользовательской привязки, и при обнаружении элемента привязки HTTP его `KeepAliveEnabled` свойства `false`. Свойство `KeepAliveEnabled` не представлено напрямую в привязке `BasicHttpBinding`, поэтому необходимо создать пользовательскую привязку, чтобы перейти вниз к элементу привязки и присвоить этому свойству значение.  
  
### <a name="to-modify-a-system-provided-binding"></a>Изменение привязки, предоставляемой системой  
  
1.  Создайте экземпляр класса <xref:System.ServiceModel.BasicHttpBinding> и установите для него режим безопасности на уровне сообщений.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  Создайте пользовательскую привязку из привязки и создайте класс <xref:System.ServiceModel.Channels.BindingElementCollection> из одного из свойств пользовательской привязки.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  Выполните цикл по классу <xref:System.ServiceModel.Channels.BindingElementCollection> и при нахождении класса <xref:System.ServiceModel.Channels.HttpTransportBindingElement> присвойте его свойству <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> значение `false`.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)
