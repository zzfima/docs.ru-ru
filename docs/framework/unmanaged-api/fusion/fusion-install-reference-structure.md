---
title: Структура FUSION_INSTALL_REFERENCE
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e81fb7c99b9fd03a69456a84f2191770f40121d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795344"
---
# <a name="fusion_install_reference-structure"></a>Структура FUSION_INSTALL_REFERENCE
Представляет ссылку, которую приложение делает с сборкой, установленной приложением в глобальном кэше сборок.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`cbSize`|Размер структуры в байтах.|  
|`dwFlags`|Зарезервировано для будущего расширения. Это значение должно быть равно 0 (нулю).|  
|`guidScheme`|Сущность, которая добавляет ссылку. Это поле может иметь одно из следующих значений:<br /><br /> - FUSION_REFCOUNT_MSI_GUID: На сборку ссылается приложение, установленное с помощью установщик Windows Майкрософт. Поле имеет `szNonCanonicalData` значение, а поле имеет значение `Windows Installer`. `MSI` `szIdentifier` Эта схема используется для параллельных сборок Windows.<br />- FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: На сборку ссылается приложение, которое отображается в интерфейсе " **Установка и удаление программ** ". Поле предоставляет маркер, регистрирующий приложение с помощью интерфейса « **Установка и удаление программ».** `szIdentifier`<br />- FUSION_REFCOUNT_FILEPATH_GUID: На сборку ссылается приложение, представленное файлом в файловой системе. `szIdentifier` Поле предоставляет путь к этому файлу.<br />- FUSION_REFCOUNT_OPAQUE_STRING_GUID: На сборку ссылается приложение, представленное только непрозрачной строкой. `szIdentifier` Поле предоставляет эту непрозрачную строку. Глобальный кэш сборок не проверяет наличие непрозрачных ссылок при удалении этого значения.<br />- FUSION_REFCOUNT_OSINSTALL_GUID: Это значение зарезервировано.|  
|`szIdentifier`|Уникальная строка, идентифицирующая приложение, которое установило сборку в глобальный кэш сборок. Его значение зависит от значения `guidScheme` поля.|  
|`szNonCanonicalData`|Строка, понятная только сущности, которая добавляет ссылку. Глобальный кэш сборок хранит эту строку, но не использует ее.|  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры Fusion](fusion-structures.md)
- [Глобальный кэш сборок](../../app-domains/gac.md)
