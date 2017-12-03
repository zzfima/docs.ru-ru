---
title: ServiceAuthorizationBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd22cd7e7783a67e7ad10371533eee680bd3af16
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="serviceauthorizationbehavior"></a>ServiceAuthorizationBehavior
ServiceAuthorizationBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceAuthorizationBehavior не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceAuthorizationBehavior имеет следующие свойства.  
  
### <a name="impersonatecallerforalloperations"></a>ImpersonateCallerForAllOperations  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, которое определяет, будет ли служба пытаться производить олицетворение при помощи учетных данных, содержащихся во входящем сообщении.  
  
### <a name="principalpermissionmode"></a>PrincipalPermissionMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Участник, используемый для выполнения операций на сервере.  
  
### <a name="roleprovider"></a>RoleProvider  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Имя поставщика ролей ASP.NET.  
  
### <a name="serviceauthorizationmanager"></a>ServiceAuthorizationManager  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Диспетчер авторизации, используемый для пользовательской авторизации.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
