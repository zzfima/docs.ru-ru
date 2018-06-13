---
title: Безопасность поведений
ms.date: 03/30/2017
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: c1360a5b9e4b96c66b4bb7809fc139d1306730dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499523"
---
# <a name="behavior-security"></a>Безопасность поведений
В этом разделе приведены образцы, демонстрирующие настройку безопасности для поведения служб.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Поведение аудита службы](../../../../docs/framework/wcf/samples/service-auditing-behavior.md)  
 Этот образец демонстрирует, как использовать <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> для включения аудита событий безопасности во время выполнения операций службы.  
  
 [Поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 В этом образце показано, как служба может с помощью поставщиков членства и ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] выполнять проверку подлинности и авторизацию клиентов.  
  
 [Авторизация доступа к операциям службы](../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 В этом примере демонстрируется использование [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) включить <xref:System.Security.Permissions.PrincipalPermissionAttribute> атрибут для авторизации доступа к операциям службы.  
  
 [Олицетворение клиента](../../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 В этом образце показано, как олицетворять приложение абонента в службе таким образом, чтобы служба могла получить доступ к ресурсам системы от лица абонента.
