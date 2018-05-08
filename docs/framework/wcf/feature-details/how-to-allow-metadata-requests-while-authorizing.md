---
title: Практическое руководство. Разрешение запросов метаданных в процессе авторизации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: 2f855080cf3ba4cee08470af77c52945e47a2ec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>Практическое руководство. Разрешение запросов метаданных в процессе авторизации
В процессе настраиваемой авторизации может потребоваться разрешить обработку запроса для метаданных. Следующий раздел содержит пошаговое руководство для проверки такого запроса.  
  
 Дополнительные сведения об авторизации Windows Communication Foundation (WCF) см. в разделе [авторизации](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>Разрешение запросов метаданных в процессе авторизации  
  
1.  Создайте расширение класса <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
2.  Переопределите метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Метод возвращает логическое значение `true` или `false`, в зависимости от того, разрешена ли авторизация. Информация о текущей процедуре находится в классе <xref:System.ServiceModel.OperationContext> и передается как параметр методу.  
  
3.  При переопределении проверяются имя контракта, пространство имен и действие, как показано в следующем примере. При выполнении этих условий возвращается логическое значение `true.`  
  
4.  Используйте точку расширения для использования класса. Дополнительные сведения см. в разделе [как: Создание пользовательского диспетчера авторизации для службы](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md).  
  
## <a name="example"></a>Пример  
 В следующем примере показано переопределение метода <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Управление утверждениями и авторизацией с помощью модели удостоверения](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)
