---
title: "Одноранговый канал"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e06a2efb-8e70-4299-8b0f-bfb37efb074b
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3d4be309a114fbf8c67e5685f83758ca09f2ff27
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="peer-channel"></a>Одноранговый канал
В этом разделе перечислены все исключения, создаваемые одноранговыми каналами каналов [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|InsufficientCredentials|Указанных учетных данных недостаточно для выполнения запрашиваемой операции. Укажите допустимое значение для заданной операции.|  
|InvalidResolverMode|Указанное значение PeerResolverMode недопустимо. Укажите значение PeerResolveMode.Auto, Default или PNRP.|  
|PeerNodeAborted|Не удается открыть PeerNode, поскольку он был завершен.|  
|PeerNullRegistrationInfo|Сведения о регистрации не могут быть пустыми. Проверьте, что операция Register вызывается с допустимым объектом RegistrationInfo.|  
|PeerNullResolveInfo|Сведения о разрешении не могут иметь значение `null`. Проверьте, что операция Resolve вызывается с допустимым объектом ResolveInfo.|
