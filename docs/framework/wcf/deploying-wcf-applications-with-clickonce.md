---
title: "Развертывание приложений WCF с помощью ClickOnce | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Развертывание приложений WCF с помощью ClickOnce
Клиентские приложения, использующие [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], могут развертываться с использованием технологии ClickOnce.Эта технология позволяет им использовать преимущества средств защиты среды выполнения, предоставляемых управлением доступом для кода, если приложения снабжены цифровой подписью с надежным сертификатом.Сертификат, используемый для подписывания приложения ClickOnce, должен располагаться в хранилище надежных издателей, а локальная политика безопасности на клиентском компьютере должна быть настроена таким образом, чтобы предоставлять разрешения полного доверия приложениям, подписанным с использованием сертификата издателя.  
  
 Дополнительные сведения по настройке приложений ClickOnce и надежных издателей см. в разделе [Настройка надежных издателей ClickOnce](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## См. также  
 [Общие сведения о развертывании надежных приложений](http://go.microsoft.com/fwlink/?LinkId=94775)   
 [Развертывание ClickOnce для приложений Windows Forms](http://go.microsoft.com/fwlink/?LinkId=94776)