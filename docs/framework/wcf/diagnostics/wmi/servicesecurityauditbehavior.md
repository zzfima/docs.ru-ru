---
title: ServiceSecurityAuditBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ea9c04c201ff022fcea54b81a998b7020fb2a836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior
ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
