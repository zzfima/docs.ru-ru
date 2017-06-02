---
title: "Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "безопасность [WCF], создание пользовательских привязок"
ms.assetid: 203a9f9e-3a73-427c-87aa-721c56265b29
caps.latest.revision: 19
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 19
---
# Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предусмотрено несколько предоставляемых системой привязок, подлежащих настройке, однако не способных в полной мере обеспечить гибкость настройки всех параметров безопасности, поддерживаемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. В этом разделе описывается создание пользовательской привязки непосредственно из отдельных элементов привязки с рассмотрением некоторых из параметров безопасности, которые могут быть заданы при создании такой привязки. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]создании пользовательских привязок см. в разделе [расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
> [!WARNING]
>  <xref:System.ServiceModel.Channels.SecurityBindingElement> не поддерживает <xref:System.ServiceModel.Channels.IDuplexSessionChannel> форму, который является по умолчанию используется формами каналов TCP канала транспорта, если <xref:System.ServiceModel.TransferMode> равен <xref:System.ServiceModel.TransferMode.Buffered>. Необходимо задать <xref:System.ServiceModel.TransferMode> для <xref:System.ServiceModel.TransferMode.Streamed> для использования <xref:System.ServiceModel.Channels.SecurityBindingElement> в этом сценарии.  
  
## <a name="creating-a-custom-binding"></a>Создание пользовательской привязки  
 В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] все привязки состоят из *элементов привязки*. Каждый элемент привязки наследуется от <xref:System.ServiceModel.Channels.BindingElement> класса. В случае стандартных предоставляемых системой привязок элементы привязки уже созданы и настроены, хотя значения некоторых свойств можно изменить.  
  
 Напротив, для создания пользовательской привязки, элементы привязки создаются и настраиваются и <xref:System.ServiceModel.Channels.CustomBinding> создается из элементов привязки.  
  
 Чтобы сделать это, добавьте отдельные элементы привязки в коллекции, представленной экземпляром <xref:System.ServiceModel.Channels.BindingElementCollection> класса, а затем установите `Elements` свойства `CustomBinding` равным этому объекту. Добавлять элементы привязки необходимо в следующем порядке: Transaction Flow, Reliable Session, Security, Composite Duplex, One-way, Stream Security, Message Encoding и Transport. Обратите внимание, что все перечисленные элементы привязки являются обязательными для каждой привязки.  
  
## <a name="securitybindingelement"></a>SecurityBindingElement  
 Безопасность на уровне сообщений, которые являются производными от связаны три элемента привязки <xref:System.ServiceModel.Channels.SecurityBindingElement> класса. Эти три элемента называются <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, и <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> используется для обеспечения смешанного режима безопасности. Другие два элемента используются, когда безопасность обеспечивается уровнем сообщений.  
  
 При обеспечении безопасности на транспортном уровне используются дополнительные классы:  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
-   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
## <a name="required-binding-elements"></a>Обязательные элементы привязки  
 Существует большое количество возможных элементов привязки, которые можно сочетать в одной привязке. При этом не все сочетания являются допустимыми. В этом разделе описываются обязательные элементы, которые должны присутствовать в привязке безопасности.  
  
 Допустимые привязки безопасности зависят от многих факторов, в том числе:  
  
-   режима безопасности;  
  
-   транспортного протокола;  
  
-   шаблона обмена сообщениями (MEP), заданного в контракте.  
  
 В следующей таблице приведены допустимые конфигурации стека элементов привязки для каждого сочетания перечисленных выше факторов. Эти конфигурации представляют собой минимальные требования. В привязку можно добавлять дополнительные элементы, такие как элементы для кодирования сообщений, элементы для транзакций и другие.  
  
|Режим безопасности|Transport|Шаблон обмена сообщениями в контракте|Шаблон обмена сообщениями в контракте|Шаблон обмена сообщениями в контракте|  
|-------------------|---------------|---------------------------------------|---------------------------------------|---------------------------------------|  
|||`Datagram`|`Request Reply`|`Duplex`|  
|Transport|HTTPS||||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP||||  
|||OneWayBindingElement|||  
|||SSL или Windows StreamSecurityBindingElement|SSL или Windows StreamSecurityBindingElement|SSL или Windows StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Сообщение|HTTP|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement|SymmetricSecurityBindingElement (режим проверки подлинности = SecureConversation)|  
|||||CompositeDuplexBindingElement|  
|||OneWayBindingElement||OneWayBindingElement|  
|||HttpTransportBindingElement|HttpTransportBindingElement|HttpTransportBindingElement|  
||TCP|SecurityBindingElement|SecurityBindingElement|SymmetricSecurityBindingElement (режим проверки подлинности = SecureConversation)|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
|Смешанный (транспорта с учетными данными сообщения)|HTTPS|TransportSecurityBindingElement|TransportSecurityBindingElement||  
|||OneWayBindingElement|||  
|||HttpsTransportBindingElement|HttpsTransportBindingElement||  
||TCP|TransportSecurityBindingElement|SymmetricSecurityBindingElement (режим проверки подлинности = SecureConversation)|SymmetricSecurityBindingElement (режим проверки подлинности = SecureConversation)|  
|||OneWayBindingElement|||  
|||SSL или Windows StreamSecurityBindingElement|SSL или Windows StreamSecurityBindingElement|SSL или Windows StreamSecurityBindingElement|  
|||TcpTransportBindingElement|TcpTransportBindingElement|TcpTransportBindingElement|  
  
 Обратите внимание, что у элементов привязки безопасности имеется ряд настраиваемых параметров. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Безопасные диалоги и безопасные сеансы](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md).  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-create-a-custom-binding-that-uses-a-symmetricsecuritybindingelement"></a>Создание пользовательской привязки с использованием элемента SymmetricSecurityBindingElement  
  
1.  Создайте экземпляр <xref:System.ServiceModel.Channels.BindingElementCollection> класс с именем `outputBec`.  
  
2.  Вызовите статический метод `M:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement(true)`, который возвращает экземпляр <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> класса.  
  
3.  Добавить <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> в коллекцию (`outputBec`) путем вызова `Add` метод <xref:System.Collections.ObjectModel.Collection%601> из <xref:System.ServiceModel.Channels.BindingElement> класса.  
  
4.  Создайте экземпляр <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> и добавьте его к коллекции (`outputBec`). Этим задается кодирование, используемое привязкой.  
  
5.  Создание <xref:System.ServiceModel.Channels.HttpTransportBindingElement> и добавьте его к коллекции (`outputBec`). Этим указывается, что привязка использует транспорт по протоколу HTTP.  
  
6.  Создайте новую пользовательскую привязку, создавая экземпляр <xref:System.ServiceModel.Channels.CustomBinding> класса и передачи коллекции `outputBec` в конструктор.  
  
7.  Полученный Пользовательская привязка обладает многими из характеристик стандартной <xref:System.ServiceModel.WSHttpBinding>. Она предусматривает безопасность уровня сообщений и учетные данные Windows (однако отключает безопасные сеансы), требует внештатного задания учетных данных службы и не шифрует подписи. Последним можно управлять только заданием <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A> свойства, как показано в шаге 4. Другими двумя можно управлять с помощью параметров стандартной привязки.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Следующий пример представляет собой полноценную функцию для создания пользовательской привязки, который использует <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
### <a name="code"></a>Код  
 [!code-csharp[c_CustomBinding#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#20)]
 [!code-vb[c_CustomBinding#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombinding/vb/source.vb#20)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>   
 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Предоставляемые системой привязки](../../../../docs/framework/wcf/system-provided-bindings.md)