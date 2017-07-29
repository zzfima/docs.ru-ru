---
title: "Устранение рисков. Контекст AuthorizationContext по умолчанию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 48363d0f8e515b703e49761a763379566e217844
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-default-authorizationcontext"></a>Устранение рисков. Контекст AuthorizationContext по умолчанию
В [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] изменена реализация контекста <xref:System.IdentityModel.Policy.AuthorizationContext>, возвращаемого при вызове <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> с аргументом `null``authorizationPolicies`.  
  
## <a name="impact"></a>Последствия  
 В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении.  
  
## <a name="mitigation"></a>Уменьшение  
 К прежнему поведению можно вернуться двумя способами.  
  
-   Перекомпилируйте приложение для ориентации на версию .NET Framework, предшествующую 4.6. Для служб, размещенных в IIS, используйте элемент `<httpRuntime targetFramework="x.x" />` для выбора более ранней версии .NET Framework в качестве целевой платформы.  
  
-   Добавьте следующую строку в раздел `<appSettings>` файла app.config.  
  
    ```xml  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

