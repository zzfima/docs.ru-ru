---
title: Основные сведения об уровне защиты
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
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 0c034608-a1ac-4007-8287-b1382eaa8bf2
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4b079d7f6e22f0c1904433c2822b92da91923ef2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="understanding-protection-level"></a>Основные сведения об уровне защиты
Свойство `ProtectionLevel` обнаруживается во многих классах, например в классах <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute>. Это свойство определяет, как защищается часть сообщения (или все сообщение). В данном разделе рассматривается эта функция [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] и принцип ее работы.  
  
 Инструкции для установки уровня защиты см. в разделе [как: Установка свойства ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md).  
  
> [!NOTE]
>  Уровни защиты можно задавать только в коде, а не в конфигурации.  
  
## <a name="basics"></a>Основные сведения  
 Ниже приведены основные сведения о возможности уровня защиты.  
  
-   Для любой части сообщения существуют три базовых уровня защиты. Для свойства (где бы оно ни появлялось) задается одно из значений перечисления <xref:System.Net.Security.ProtectionLevel>. Эти значения указаны ниже в порядке возрастания уровня защиты.  
  
    -   `None`.  
  
    -   `Sign`. Защищенная часть подписывается цифровой подписью. Это гарантирует защиту защищенной части сообщения от любой подделки.  
  
    -   `EncryptAndSign`. Для обеспечения конфиденциальности часть сообщения перед подписанием шифруется.  
  
-   Можно задать требования к защите только для *данные приложения* с помощью этой функции. Например, заголовки WS-Addressing являются данными инфраструктуры и, следовательно, `ProtectionLevel` их не затрагивает.  
  
-   Когда для режима безопасности задано значение `Transport`, все сообщение защищается механизмом транспорта. Поэтому установка отдельного уровня защиты для разных частей сообщения не имеет эффекта.  
  
-   `ProtectionLevel` Дает разработчику задать *минимальный уровень* , которому должна соответствовать привязка. Когда служба развернута, фактическая привязка, заданная в конфигурации, может поддерживать или не поддерживать этот минимальный уровень. Например, по умолчанию класс <xref:System.ServiceModel.BasicHttpBinding> не обеспечивает безопасность (хотя обеспечение безопасности может быть включено). Поэтому использование этого класса с контрактом, параметр которого отличен от `None`, будет приводить к вызову исключения.  
  
-   Если служба требует, чтобы минимальный уровень `ProtectionLevel` для всех сообщений был `Sign`, клиент (возможно, созданный не технологией [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]) может шифровать и подписывать все сообщения (что превышает требуемый минимум). В этом случае [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] не будет вызывать исключение, поскольку действия клиента превышают минимальное требование. Однако следует иметь в виду, что приложения [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (службы или клиенты) по возможности не будут чрезмерно защищать часть сообщения, а будут обеспечивать соответствие минимальному уровню. Обратите также внимание, что при использовании режима `Transport` в качестве режима безопасности транспорт может чрезмерно защищать поток сообщений, поскольку он не способен обеспечить защиту на более детальном уровне.  
  
-   Если для `ProtectionLevel` явно задается значение `Sign` или `EncryptAndSign`, необходимо использовать привязку с разрешенным обеспечением безопасности. В противном случае будет вызвано исключение.  
  
-   Если выбирается привязка, разрешающая обеспечение безопасности, а свойство `ProtectionLevel` нигде в контракте не задается, все данные приложений будут шифроваться и подписываться.  
  
-   Если выбирается привязка, в которой не разрешено обеспечение безопасности (например, в классе `BasicHttpBinding` обеспечение безопасности запрещено по умолчанию), и уровень `ProtectionLevel` явно не задан, данные приложений защищаться не будут.  
  
-   Если используется привязка, которая обеспечивает безопасность на транспортном уровне, все данные приложений будут защищаться в соответствии с возможностями транспорта.  
  
-   Если используется привязка, которая обеспечивает безопасность на уровне сообщений, данные приложений будут защищаться в соответствии с уровнями защиты, заданными в контракте. Если уровень защиты не задается, все данные приложений в сообщениях будут шифроваться и подписываться.  
  
-   `ProtectionLevel` можно задать на разных уровнях области действия. Существует иерархия, связанная с областью действия, которая рассматривается в следующем разделе.  
  
## <a name="scoping"></a>Область действия  
 При задании `ProtectionLevel` на самом верхнем API задается уровень для всех уровней ниже данного. Если для `ProtectionLevel` задается другое значение на более низком уровне, все интерфейсы API, расположенные ниже этого уровня в иерархии, сбрасываются на этот новый уровень (однако интерфейсы API, расположенные выше этого уровня, остаются под влиянием самого верхнего уровня). Иерархия имеет представленный ниже вид. Атрибуты на одном и том же уровне являются одноранговыми.  
  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
 <xref:System.ServiceModel.FaultContractAttribute>  
  
 <xref:System.ServiceModel.MessageContractAttribute>  
  
 <xref:System.ServiceModel.MessageHeaderAttribute>  
  
 <xref:System.ServiceModel.MessageBodyMemberAttribute>  
  
## <a name="programming-protectionlevel"></a>Программирование ProtectionLevel  
 Чтобы запрограммировать `ProtectionLevel` в любом месте иерархии, задайте для этого свойства соответствующее значение при применении атрибута. Примеры см. в разделе [как: Установка свойства ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md).  
  
> [!NOTE]
>  Чтобы задать данное свойство в контрактах сбоев и сообщений, необходимо понимать работу этих возможностей. Дополнительные сведения см. в разделе [как: Установка свойства ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md) и [использование контрактов сообщений](../../../docs/framework/wcf/feature-details/using-message-contracts.md).  
  
## <a name="ws-addressing-dependency"></a>Зависимость от WS-Addressing  
 В большинстве случаев с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания клиента гарантирует, что клиент и служба контракты идентичны. Однако одинаковые на первый взгляд контракты могут приводить к вызову клиентом исключения. Это происходит всякий раз, когда привязка не поддерживает спецификацию WS-Addressing и в контракте определено несколько уровней защиты. Например, это происходит при использовании класса <xref:System.ServiceModel.BasicHttpBinding>, не поддерживающего данную спецификацию, или при создании пользовательской привязки, которая не поддерживает WS-Addressing. Чтобы в одном контракте разрешить разные уровни защиты, функция `ProtectionLevel` полагается на спецификацию WS-Addressing. Если привязка не поддерживает спецификацию WS-Addressing, для всех уровней задается один и тот же уровень защиты. В качестве фактического уровня защиты для всех областей в контракте задается уровень самой мощной защиты, используемый в контракте.  
  
 Это может привести к проблеме, которую на первый взгляд сложно устранить. Можно создать контракт клиента (интерфейс), который содержит методы для нескольких служб. То есть для создания клиента, взаимодействующего с несколькими службами, используется один и тот же интерфейс, и этот единственный интерфейс содержит методы для всех служб. Разработчику следует быть внимательным в этом редком сценарии, чтобы обеспечить вызов только тех методов, которые подходят для каждой конкретной службы. Если привязкой является класс <xref:System.ServiceModel.BasicHttpBinding>, поддержка нескольких уровней защиты невозможна. Однако служба, отвечающая клиенту, может ответить и клиенту с более низким уровнем защиты, чем требуется. В этом случае клиент вызовет исключение, поскольку он ожидает более высокий уровень защиты.  
  
 В примере кода иллюстрируется эта проблема. В представленном ниже примере показаны контракты службы и клиента. Предположим, что привязка используется [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) элемента. Следовательно, все операции в контракте имеют один и тот же уровень защиты. Этот одинаковый уровень защиты определяется как максимальный уровень защиты для всех операций.  
  
 Ниже приведен контракт службы:  
  
 [!code-csharp[c_ProtectionLevel#7](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#7)]
 [!code-vb[c_ProtectionLevel#7](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#7)]  
  
 В следующем коде показан интерфейс контракта клиента. Обратите внимание, что он содержит метод `Tax`, предназначенный для использования с другой службой:  
  
 [!code-csharp[c_ProtectionLevel#8](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#8)]
 [!code-vb[c_ProtectionLevel#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#8)]  
  
 Когда клиент вызывает метод `Price`, при получении ответа от службы он вызывает исключение. Причина этого в том, что клиент не задает `ProtectionLevel` в `ServiceContractAttribute` и, следовательно, использует значение по умолчанию (<xref:System.Net.Security.ProtectionLevel.EncryptAndSign>) для всех методов, включая метод `Price`. Однако служба возвращает значение, используя уровень <xref:System.Net.Security.ProtectionLevel.Sign>, поскольку контракт службы определяет единственный метод, в качестве уровня защиты которого задано значение <xref:System.Net.Security.ProtectionLevel.Sign>. В этом случае при проверке ответа от службы клиент вызовет ошибку.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 <xref:System.ServiceModel.FaultContractAttribute>  
 <xref:System.ServiceModel.MessageContractAttribute>  
 <xref:System.ServiceModel.MessageHeaderAttribute>  
 <xref:System.ServiceModel.MessageBodyMemberAttribute>  
 <xref:System.Net.Security.ProtectionLevel>  
 [Защита служб](../../../docs/framework/wcf/securing-services.md)  
 [Практическое руководство. Установка свойства ProtectionLevel](../../../docs/framework/wcf/how-to-set-the-protectionlevel-property.md)  
 [Указание и обработка сбоев в контрактах и службах](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)  
 [Использование контрактов сообщений](../../../docs/framework/wcf/feature-details/using-message-contracts.md)
