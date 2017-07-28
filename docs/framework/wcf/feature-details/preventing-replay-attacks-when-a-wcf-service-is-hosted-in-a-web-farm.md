---
title: "Предотвращение атак воспроизведения, когда служба WCF размещена на веб-ферме | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c2ed695-7a31-4257-92bd-9e9731b886a5
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Предотвращение атак воспроизведения, когда служба WCF размещена на веб-ферме
При использовании безопасности сообщений WCF предотвращает атаки путем воспроизведения NONCE из входящего сообщения и проверки внутренней`InMemoryNonceCache`, чтобы убедиться в том, что в нем присутствует созданный NONCE.Если он там есть, то сообщение удаляется как повторное.Когда служба WCF размещается в веб\-ферме, свойство `InMemoryNonceCache` не разделяется всеми узлами веб\-фермы и служба уязвима для атак с повторением пакетов.Для устранения подобной угрозы сценарий WCF 4.5 предоставляет точку расширяемости, которая позволяет реализовать собственный кэш NONCE. Это осуществляется наследованием класса от абстрактного класса <xref:System.ServiceModel.Security.NoneCache>.  
  
## Реализация NoneCache  
 Чтобы реализовать собственный кэш общего NONCE, унаследуйте класс от <xref:System.ServiceModel.Security.NoneCache> и переопределите метод [M:System.ServiceModel.Security.NoneCache.CheckNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.CheckNonce%2A> и [M:System.ServiceModel.Security.NoneCache.TryAddNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.TryAddNonce%2A>.[M:System.ServiceModel.Security.NoneCache.CheckNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.CheckNonce%2A> будет проверять, существует ли указанный NONCE в кэше.[M:System.ServiceModel.Security.NoneCache.TryAddNonce\(System.Byte\<xref:System.ServiceModel.Security.NoneCache.TryAddNonce%2A> будет пытаться добавить NONCE в кэш.После реализации класса создается его экземпляр, который назначается объекту <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalClientSecuritySettings.NonceCache%2A> для обнаружения повторных сообщений на стороне клиента и назначается объекту <xref:System.ServiceModel.Channels.SecurityBindingElement.LocalServiceSecuritySettings.NonceCache%2A> для обнаружения подобных атак на стороне сервера.Для этой функции нет стандартной конфигурации параметров.  
  
## См. также  
 [Безопасность обмена сообщениями](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [SymmetricSecurityBindingElement](../../../../docs/framework/wcf/diagnostics/wmi/symmetricsecuritybindingelement.md)