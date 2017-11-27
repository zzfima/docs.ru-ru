---
title: "Практическое руководства. Создание SecurityBindingElement для заданного режима проверки подлинности"
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
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 658eaf3469e0be179c78d9963687e6de9cb7fc00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a>Практическое руководства. Создание SecurityBindingElement для заданного режима проверки подлинности
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] имеется несколько режимов, с помощью которых клиенты и службы проверяют подлинность друг друга. Для этих режимов проверки подлинности можно создать привязки безопасности с помощью статических методов класса <xref:System.ServiceModel.Channels.SecurityBindingElement> или с помощью конфигурации, как показано в следующем примере кода.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]18 режимов проверки подлинности, в разделе [режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).  
  
## <a name="example"></a>Пример  
 В следующем примере кода показаны методы создания привязок для различных методов проверки подлинности.  
  
> [!NOTE]
>  После создания объекта <xref:System.ServiceModel.Channels.SecurityBindingElement> некоторые свойства являются неизменяемыми, такие как <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> и <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>. Вызов `set` для этих свойств не изменяет их.  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a>См. также  
 [Режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 [Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
