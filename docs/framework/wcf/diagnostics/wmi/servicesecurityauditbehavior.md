---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: dc48b8742c60714720be3cf4b22ba672f73c720a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570230"
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior
ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceSecurityAuditBehavior не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceSecurityAuditBehavior имеет следующие свойства.  
  
### <a name="auditloglocation"></a>AuditLogLocation  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Местоположение журнала аудита.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Тип уровня проверки подлинности сообщений, используемый для записи в журнал событий аудита.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Типы событий авторизации, записываемых в журнал аудита.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
