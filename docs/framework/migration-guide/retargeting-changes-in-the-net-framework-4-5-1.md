---
title: "Изменения целевой платформы в .NET Framework 4.5.1 | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application compatibility
- retargeting changes
- .NET Framework 4.5.1
- retargeting changes, .NET Framework 4.5.1
- retargeting changes, .NET Framework
ms.assetid: 8087326d-77e9-4804-ba33-ff1bb1bec2b8
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0c497561254c0f97f22ac05c7d44224b30ef74d0
ms.lasthandoff: 04/18/2017

---
# <a name="retargeting-changes-in-the-net-framework-451"></a>Изменения целевой платформы в .NET Framework 4.5.1
В редких случаях изменения целевой платформы могут повлиять на приложения, которые перекомпилируются для использования в [!INCLUDE[net_v451](../../../includes/net-v451-md.md)]. Они не влияют на двоичные файлы, предназначенные для предыдущей версии .NET Framework, но влияют в случае установленной версии 4.5.1. [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] содержит изменения целевой платформы в следующих областях.  
  
-   [Ядро](#Core)  
  
-   [ADO.NET](#ADO)  
  
-   [MSBuild](#MSBuild)  
  
 Столбец "Scope" в следующих таблицах определяет важность каждого изменения.  
  
-   Основное. Значительное изменение, влияющее на большое количество приложений или требующее существенного изменения кода. Обратите внимание, что ни одно из изменений целевой платформы не попадает в эту категорию.  
  
-   Незначительное. Изменение влияет на небольшое количество приложений или требует незначительного изменения кода.  
  
-   Пограничное. Изменение влияет на приложения в исключительных ситуациях.  
  
-   Прозрачное. Изменение не оказывает особого влияния на разработчика или пользователя приложения. При этом вносить изменения в приложения не требуется.  
  
<a name="Core"></a>   
## <a name="core-retargeting-changes"></a>Изменение целевой платформы ядра  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Атрибут <xref:System.ObsoleteAttribute?displayProperty=fullName>|При создании библиотеки метаданных Windows (WINMD-файл) атрибут <xref:System.ObsoleteAttribute> экспортируется как <xref:System.ObsoleteAttribute> и [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx).|В случае перекомпиляции существующего исходного кода, использующего атрибут <xref:System.ObsoleteAttribute>, могут выдаваться предупреждения при использовании этого кода в C++/CX или JavaScript.<br /><br /> К коду в управляемых сборках не рекомендуется применять ни <xref:System.ObsoleteAttribute>, ни [Windows.Foundation.DeprecatedAttribute](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.deprecatedattribute.aspx), так как при сборке могут выдаваться предупреждения.<br /><br /> Дополнительные сведения см. в разделе справки <xref:System.ObsoleteAttribute>.|Пограничный случай|  
  
<a name="ADO"></a>   
## <a name="adonet-retargeting-changes"></a>Изменение целевой платформы ADO.NET  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Класс <xref:System.Data.Common.DbParameter?displayProperty=fullName>|<xref:System.Data.Common.DbParameter.Precision%2A?displayProperty=fullName> и <xref:System.Data.Common.DbParameter.Scale%2A?displayProperty=fullName> реализованы как открытые виртуальные свойства. Они заменяют соответствующие явные реализации интерфейса — <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Precision%2A?displayProperty=fullName> и <xref:System.Data.Common.DbParameter.System%23Data%23IDbDataParameter%23Scale%2A?displayProperty=fullName>.|Изменение влияет только на разработчиков, которые занимаются построением поставщика базы данных ADO.NET.|Edge|  
  
<a name="MSBuild"></a>   
## <a name="msbuild-retargeting-changes"></a>Изменение целевой платформы MSBuild  
  
|Функция|Изменение|Последствия|Область|  
|-------------|------------|------------|-----------|  
|Задача `ResolveAssemblyReference`|Задача выдает предупреждение (MSB3270), которое означает, что ссылка или ее зависимости не соответствуют архитектуре приложения. Например, это происходит, если приложение, скомпилированное с параметром `anycpu`, содержит 32-разрядную ссылку. Такой сценарий может привести к сбою приложения во время выполнения (в этом случае: если приложение развертывается как 64-разрядный процесс).|Существует две области влияния.<br /><br /> – Во время перекомпиляции выдаются предупреждения, которые отсутствовали при компиляции в предыдущей версии MSBuild. Однако поскольку в предупреждении указан возможный источник ошибки среды выполнения, его следует проверить.<br />– Если предупреждения считаются ошибками, приложение скомпилировано не будет.|Дополнительный номер|  
  
## <a name="see-also"></a>См. также  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)   
 [Совместимость приложений в 4.5](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)   
 [Совместимость приложений в 4.5.2](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)
