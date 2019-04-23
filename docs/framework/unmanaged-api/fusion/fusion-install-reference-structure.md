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
ms.openlocfilehash: 611b4a543a1de7c6163ec45ff7f17d07726569ba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110369"
---
# <a name="fusioninstallreference-structure"></a>Структура FUSION_INSTALL_REFERENCE
Представляет ссылку, когда приложение устанавливает для сборки, приложение, установленной в глобальном кэше сборок.  
  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`cbSize`|Размер структуры в байтах.|  
|`dwFlags`|Зарезервировано для будущего расширения. Это значение должно быть 0 (ноль).|  
|`guidScheme`|Добавляет ссылку на сущность. Это поле может иметь одно из следующих значений:<br /><br /> -FUSION_REFCOUNT_MSI_GUID: Ссылка на сборку в приложении, был установлен с помощью установщика Microsoft Windows. `szIdentifier` Полю присваивается `MSI`и `szNonCanonicalData` поля задается значение `Windows Installer`. Эта схема используется для сборок side-by-side Windows.<br />-   FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: Ссылка на сборку приложением, которое отображается в **Add/Remove Programs** интерфейс. `szIdentifier` Поле предоставляет маркер, который регистрирует приложение с **Add/Remove Programs** интерфейс.<br />-FUSION_REFCOUNT_FILEPATH_GUID: Ссылка на сборку приложением, которое представляется с помощью файла в файловой системе. `szIdentifier` Поле предоставляет путь к этому файлу.<br />-   FUSION_REFCOUNT_OPAQUE_STRING_GUID: Приложение, которое представлено только непрозрачная строка ссылается на сборку. `szIdentifier` Поле предоставляет это непрозрачная строка. Глобальный кэш сборок не проверяет наличие непрозрачных ссылок при удалении этого значения.<br />-FUSION_REFCOUNT_OSINSTALL_GUID: Это значение зарезервировано.|  
|`szIdentifier`|Уникальная строка, определяющая приложения, которые установить сборки в глобальном кэше сборок. Его значение зависит от значения `guidScheme` поля.|  
|`szNonCanonicalData`|Строка, которая может интерпретировать только сущность, которая добавляет ссылку. Глобальный кэш сборок сохраняет полученную строку, но не использует его.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
- [Глобальный кэш сборок](../../../../docs/framework/app-domains/gac.md)
