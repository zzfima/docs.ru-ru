---
title: "Устранение рисков. Нормализация путей | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 158d47b1-ba6d-4fa6-8963-a012666bdc31
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0579bb975a62e512062b10d39c2967cdcd23438f
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-path-normalization"></a>Устранение рисков. Нормализация путей
Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], нормализация путей в .NET Framework изменилась.  
  
## <a name="what-is-path-normalization"></a>Что такое нормализация путей?  
 Нормализация пути подразумевает изменение строки, которая идентифицирует путь или файл, чтобы он соответствовал допустимому пути в целевой операционной системе. Нормализация обычно включает в себя:  
  
-   канонизацию разделителей компонентов и каталогов;  
  
-   применение текущего каталога к относительному пути;  
  
-   оценку относительного каталога (`.`) или родительского каталога (`..`) в пути;  
  
-   обрезку указанных символов.  
  
## <a name="the-changes"></a>Изменения  
 Начиная с приложений, ориентированных на [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], нормализация путей изменилась в следующих направлениях.  
  
-   Среда выполнения перекладывает нормализацию путей на функцию [GetFullPathName](https://msdn.microsoft.com/library/windows/desktop/aa364963\(v=vs.85\).aspx) операционной системы.  
  
-   Нормализация больше не предусматривает обрезки окончания сегментов каталогов (например, пробела в конце имени каталога).  
  
-   Поддержка синтаксиса пути устройства в режиме полного доверия, включая `\\.\` и (для API-интерфейсов файлового ввода-вывода в mscorlib.dll) `\\?\`.  
  
-   Среда выполнения не проверяет пути с синтаксисом устройства.  
  
-   Поддерживается использование синтаксиса устройства для доступа к альтернативным потокам данных.  
  
## <a name="impact"></a>Последствия  
 Для приложений, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, эти изменения включены по умолчанию. Они должны улучшить производительность, позволяя методам получать доступ к ранее недоступным путям.  
  
 Это изменение не влияет на приложения, предназначенные для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] и более ранних версий, но работающие на платформе [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более новой версии.  
  
## <a name="mitigation"></a>Уменьшение  
 В приложениях, предназначенных для [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, данное изменение можно отключить и использовать устаревшую нормализацию, добавив следующее в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:  
  
```xml  
  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
</runtime>  
  
```  
  
 В приложениях, предназначенных для [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] или более ранней версии, но работающих на платформе [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] или более поздней версии, можно включить изменения в нормализацию пути, добавив следующее в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:  
  
```xml  
  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=false" />    
</runtime>  
  
```  
  
## <a name="see-also"></a>См. также  
 [Изменение целевой платформы](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
