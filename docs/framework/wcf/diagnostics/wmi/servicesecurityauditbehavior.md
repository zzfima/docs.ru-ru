---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: e8b24877c2d76a3f2f90c27ae83374c7bca1328b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181164"
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
  
 Тип доступа: только для чтения  
  
 Местоположение журнала аудита.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Тип уровня проверки подлинности сообщений, используемый для записи в журнал событий аудита.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Типы событий авторизации, записываемых в журнал аудита.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, задающее поведение для подавления ошибок записи в журнал аудита.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
