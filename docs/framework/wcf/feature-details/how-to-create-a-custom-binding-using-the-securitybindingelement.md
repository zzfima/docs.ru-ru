---
title: Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating custom bindings
ms.assetid: 203a9f9e-3a73-427c-87aa-721c56265b29
ms.openlocfilehash: 7966c1fe4cd94408455c6bb146fdd3ea55757702
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316808"
---
# <a name="how-to-create-a-custom-binding-using-the-securitybindingelement"></a>Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement
Windows Communication Foundation (WCF) включает в себя несколько предоставляемых системой привязок, которые можно настроить, но не предоставляют полную гибкость при настройке все параметры безопасности, которые поддерживает WCF. В этом разделе описывается создание пользовательской привязки непосредственно из отдельных элементов привязки с рассмотрением некоторых из параметров безопасности, которые могут быть заданы при создании такой привязки. Дополнительные сведения о создании пользовательских привязок см. в разделе [расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md).  
  
> [!WARNING]
>  <xref:System.ServiceModel.Channels.SecurityBindingElement> не поддерживает форму канала <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, которая по умолчанию используется формами каналов TCP-транспорта, если свойство <xref:System.ServiceModel.TransferMode> имеет значение <xref:System.ServiceModel.TransferMode.Buffered>. Необходимо задать свойству <xref:System.ServiceModel.TransferMode> значение <xref:System.ServiceModel.TransferMode.Streamed> для использования элемента <xref:System.ServiceModel.Channels.SecurityBindingElement> в этом сценарии.  
  
## <a name="creating-a-custom-binding"></a>Создание пользовательской привязки  
 В WCF все привязки состоят из *элементов привязки*. Каждый элемент привязки наследуется от класса <xref:System.ServiceModel.Channels.BindingElement>. В случае стандартных предоставляемых системой привязок элементы привязки уже созданы и настроены, хотя значения некоторых свойств можно изменить.  
  
 В противоположность этому при создании пользовательской привязки потребуется создать и настроить элементы привязки и создать из этих элементов объект <xref:System.ServiceModel.Channels.CustomBinding>.  
  
 Для этого необходимо добавить отдельные элементы привязки в коллекцию, представляемую экземпляром класса <xref:System.ServiceModel.Channels.BindingElementCollection>, а затем задать свойство `Elements` класса `CustomBinding` равным этому объекту. Элементы привязки необходимо добавить в следующем порядке: Поток транзакций, надежный сеанс, безопасности, составной дуплексный канал, односторонней связи, Stream Security, кодирование сообщений и транспорта. Обратите внимание, что все перечисленные элементы привязки являются обязательными для каждой привязки.  
  
## <a name="securitybindingelement"></a>SecurityBindingElement  
 С безопасностью уровня сообщений связаны три элемента привязки; все они наследуются от класса <xref:System.ServiceModel.Channels.SecurityBindingElement>. Эти три элемента называются <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> и <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>. Элемент <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> используется для обеспечения смешанного режима безопасности. Другие два элемента используются, когда безопасность обеспечивается уровнем сообщений.  
  
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
  
 Обратите внимание, что у элементов привязки безопасности имеется ряд настраиваемых параметров. Дополнительные сведения см. в разделе [режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
 Дополнительные сведения см. в разделе [безопасных диалогах и безопасные сеансы](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md).  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-create-a-custom-binding-that-uses-a-symmetricsecuritybindingelement"></a>Создание пользовательской привязки с использованием элемента SymmetricSecurityBindingElement  
  
1. Создайте экземпляр класса <xref:System.ServiceModel.Channels.BindingElementCollection> с именем `outputBec`.  
  
2. Вызовите статический метод `M:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement(true)`, который возвращает экземпляр класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
3. Добавьте объект <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> в коллекцию (`outputBec`), вызвав метод `Add` класса <xref:System.Collections.ObjectModel.Collection%601> класса <xref:System.ServiceModel.Channels.BindingElement>.  
  
4. Создайте экземпляр класса <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> и добавьте его в коллекцию (`outputBec`). Этим задается кодирование, используемое привязкой.  
  
5. Создайте объект <xref:System.ServiceModel.Channels.HttpTransportBindingElement> и добавьте его в коллекцию (`outputBec`). Этим указывается, что привязка использует транспорт по протоколу HTTP.  
  
6. Создайте новую пользовательскую привязку путем создания экземпляра класса <xref:System.ServiceModel.Channels.CustomBinding> и передачи коллекции `outputBec` конструктору.  
  
7. Полученная пользовательская привязка обладает многими из характеристик стандартной привязки <xref:System.ServiceModel.WSHttpBinding>. Она предусматривает безопасность уровня сообщений и учетные данные Windows (однако отключает безопасные сеансы), требует внештатного задания учетных данных службы и не шифрует подписи. Последним можно управлять, только если определить свойство <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A>, как показано на шаге 4. Другими двумя можно управлять с помощью параметров стандартной привязки.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 Следующий пример кода представляет собой полноценную функцию для создания пользовательской привязки с использованием класса <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
### <a name="code"></a>Код  
 [!code-csharp[c_CustomBinding#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombinding/cs/c_custombinding.cs#20)]
 [!code-vb[c_CustomBinding#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombinding/vb/source.vb#20)]  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Расширение привязок](../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md)
