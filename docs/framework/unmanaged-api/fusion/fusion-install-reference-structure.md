---
title: "Структура FUSION_INSTALL_REFERENCE"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FUSION_INSTALL_REFERENCE
api_location: fusion.dll
api_type: COM
f1_keywords: FUSION_INSTALL_REFERENCE
helpviewer_keywords: FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 244ea215b6668685920a454c1bd9da065076f38b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="fusioninstallreference-structure"></a>Структура FUSION_INSTALL_REFERENCE
Представляет ссылку, когда приложение устанавливает на сборку, установленную приложением в глобальном кэше сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`cbSize`|Размер структуры в байтах.|  
|`dwFlags`|Зарезервировано для будущего расширения. Это значение должно быть 0 (ноль).|  
|`guidScheme`|Сущность, которая добавляет ссылку. Это поле может принимать одно из следующих значений:<br /><br /> -FUSION_REFCOUNT_MSI_GUID: Ссылку на сборку приложения, установленного с помощью установщика Windows. `szIdentifier` Имеет значение `MSI`и `szNonCanonicalData` имеет значение `Windows Installer`. Эта схема используется для сборок Windows side-by-side.<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Ссылку на сборку приложения, которое отображается в **Установка и удаление программ** интерфейса. `szIdentifier` Поле предоставляет маркер, регистрирующий приложение с **Установка и удаление программ** интерфейса.<br />-FUSION_REFCOUNT_FILEPATH_GUID: Ссылку на сборку приложения, которое представляется с помощью файла в файловой системе. `szIdentifier` Поле предоставляет путь к этому файлу.<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID: Ссылку на сборку приложения, представленного только непрозрачная строка. `szIdentifier` Поле предоставляет это непрозрачная строка. Глобальный кэш сборок не проверяет наличие непрозрачных ссылок при удалении этого значения.<br />-FUSION_REFCOUNT_OSINSTALL_GUID: Это значение зарезервировано.|  
|`szIdentifier`|Уникальная строка, идентифицирующая приложения, которая установлена сборка в глобальном кэше сборок. Его значение зависит от значения `guidScheme` поля.|  
|`szNonCanonicalData`|Строка, которая может интерпретировать только сущность, которая добавляет ссылку. Глобальный кэш сборок эта строка хранится, но не используется.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Структуры Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)  
 [Глобальный кэш сборок](../../../../docs/framework/app-domains/gac.md)
