---
title: "Одноранговый канал | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e06a2efb-8e70-4299-8b0f-bfb37efb074b
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Одноранговый канал
В этом разделе перечислены все исключения, создаваемые одноранговыми каналами каналов [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## Список исключений  
  
|Код ресурса|Строка ресурса|  
|-----------------|--------------------|  
|InsufficientCredentials|Указанных учетных данных недостаточно для выполнения запрашиваемой операции.  Укажите допустимое значение для заданной операции.|  
|InvalidResolverMode|Указанное значение PeerResolverMode недопустимо.  Укажите значение PeerResolveMode.Auto, Default или PNRP.|  
|PeerNodeAborted|Не удается открыть PeerNode, поскольку он был завершен.|  
|PeerNullRegistrationInfo|Сведения о регистрации не могут быть пустыми.  Проверьте, что операция Register вызывается с допустимым объектом RegistrationInfo.|  
|PeerNullResolveInfo|Сведения о разрешении не могут иметь значение `null`.  Проверьте, что операция Resolve вызывается с допустимым объектом ResolveInfo.|