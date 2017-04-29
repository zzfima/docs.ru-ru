---
title: "Устранение рисков. Контекст AuthorizationContext по умолчанию | Документация Майкрософт"
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
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d2cffc531efc0f0be841956d3a09e1ab253d8fbd
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-default-authorizationcontext"></a>Устранение рисков. Контекст AuthorizationContext по умолчанию
Реализация <xref:System.IdentityModel.Policy.AuthorizationContext>, возвращенная путем вызова <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> с аргументом `null``authorizationPolicies`, изменила реализацию в [!INCLUDE[net_v46](../../../includes/net-v46-md.md)].  
  
## <a name="impact"></a>Последствия  
 В редких случаях в приложениях WCF, которые используют настраиваемую проверку подлинности, могут возникать различия в поведении.  
  
## <a name="mitigation"></a>Уменьшение  
 К прежнему поведению можно вернуться двумя способами.  
  
-   Перекомпилируйте приложение для ориентации на версию .NET Framework, предшествующую 4.6. Для служб, размещенных в IIS, используйте элемент `<httpRuntime targetFramework="x.x" />` для выбора более ранней версии .NET Framework в качестве целевой платформы.  
  
-   Добавьте следующую строку в раздел `<appSettings>` файла app.config.  
  
    ```  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
