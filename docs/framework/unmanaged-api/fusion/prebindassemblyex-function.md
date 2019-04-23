---
title: Функция PreBindAssemblyEx
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8251d21fe535f85cc6abd0a7bc6c96ab320007f0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090242"
---
# <a name="prebindassemblyex-function"></a>Функция PreBindAssemblyEx
Возвращает после применения политики отображаемое имя сборки.  
  
 Эта функция поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a>Параметры  
 `pAppCtx`  
 [in] Определяет контекст приложения.  
  
 `pName`  
 [in] Обозначает имя сборки.  
  
 `pAsmParent`  
 [in] Идентифицирует родительской сборки. Этот параметр не учитывается.  
  
 `pwzRuntimeVersion`  
 [in] Определяет версию среды выполнения.  
  
 `ppNamePostPolicy`  
 [out] Содержит имя отображаемое после применения политики.  
  
 `pvReserved`  
 [in] Зарезервировано для будущего расширения. `pvReserved` должен быть пустой ссылкой.  
  
## <a name="remarks"></a>Примечания  
 `ppNamePostPolicy` Выходной параметр имеет значение только в том случае, если функция возвращает значение HRESULT FUSION_E_REF_DEF_MISMATCH. В противном случае — значение null.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
