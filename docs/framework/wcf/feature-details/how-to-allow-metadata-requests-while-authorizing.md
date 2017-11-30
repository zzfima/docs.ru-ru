---
title: "Практическое руководство. Разрешение запросов метаданных в процессе авторизации"
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
helpviewer_keywords: allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 103aba5118810064c1cafb7c82634ef000ced667
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>Практическое руководство. Разрешение запросов метаданных в процессе авторизации
В процессе настраиваемой авторизации может потребоваться разрешить обработку запроса для метаданных. Следующий раздел содержит пошаговое руководство для проверки такого запроса.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)][!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] авторизации, в разделе [авторизации](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>Разрешение запросов метаданных в процессе авторизации  
  
1.  Создайте расширение класса <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
2.  Переопределите метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Метод возвращает логическое значение `true` или `false`, в зависимости от того, разрешена ли авторизация. Информация о текущей процедуре находится в классе <xref:System.ServiceModel.OperationContext> и передается как параметр методу.  
  
3.  При переопределении проверяются имя контракта, пространство имен и действие, как показано в следующем примере. При выполнении этих условий возвращается логическое значение `true.`  
  
4.  Используйте точку расширения для использования класса. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как: Создание пользовательского диспетчера авторизации для службы](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано переопределение метода <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
