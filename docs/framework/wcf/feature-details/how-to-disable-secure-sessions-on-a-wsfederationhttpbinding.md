---
title: "Как упорядочить отключения безопасных сеансов в WSFederationHttpBinding | Microsoft Docs"
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
  - "федерация"
  - "WCF, федерация"
ms.assetid: 675fa143-6a4e-4be3-8afc-673334ab55ec
caps.latest.revision: 16
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 16
---
# Как упорядочить отключения безопасных сеансов в WSFederationHttpBinding
Некоторые службы могут требовать федеративных учетных данных, но не поддерживать безопасные сеансы.В этом случае необходимо отключить функцию безопасных сеансов.В отличие от класса <xref:System.ServiceModel.WsHttpBinding>, класс <xref:System.ServiceModel.WSFederationHttpBinding> не предоставляет способа отключения безопасных сеансов при взаимодействии со службой.Вместо этого необходимо создать пользовательскую привязку, которая заменяет параметры безопасного сеанса начальной загрузкой.  
  
 В этом разделе показано, как изменить элементы привязки, содержащиеся в привязке <xref:System.ServiceModel.WSFederationHttpBinding>, чтобы создать пользовательскую привязку.Результат совпадает с <xref:System.ServiceModel.WSFederationHttpBinding>, за исключением того, что не используются безопасные сеансы.  
  
### Создание пользовательской федеративной привязки без безопасных сеансов  
  
1.  Создайте экземпляр класса <xref:System.ServiceModel.WSFederationHttpBinding> либо принудительно в коде, либо загрузив один из файлов конфигурации.  
  
2.  Клонируйте <xref:System.ServiceModel.WSFederationHttpBinding> в <xref:System.ServiceModel.Channels.CustomBinding>.  
  
3.  Найдите <xref:System.ServiceModel.Channels.SecurityBindingElement> в <xref:System.ServiceModel.Channels.CustomBinding>.  
  
4.  Найдите <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters> в <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
5.  Замените исходный элемент <xref:System.ServiceModel.Channels.SecurityBindingElement> элементом привязки безопасности начальной загрузки из <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters>.  
  
## Пример  
 В следующем примере создается пользовательская федеративная привязка без безопасных сеансов.  
  
 [!code-csharp[c_CustomFederationBinding#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customfederationbinding/cs/c_customfederationbinding.cs#0)]
 [!code-vb[c_CustomFederationBinding#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customfederationbinding/vb/c_customfederationbinding.vb#0)]  
  
## Компиляция кода  
  
-   Чтобы скомпилировать этот пример кода, создайте проект, ссылающийся на сборку System.ServiceModel.dll.  
  
## См. также  
 [Привязки и безопасность](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)