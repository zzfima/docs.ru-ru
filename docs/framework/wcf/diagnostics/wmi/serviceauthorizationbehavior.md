---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: e03f83927ec5aef7f916b2262c9c8cff1db68ac9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
