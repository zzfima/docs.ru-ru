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
ms.openlocfilehash: 8aa2d174200db76f5c7a6db43e14bb6904604226
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796328"
---
# <a name="prebindassemblyex-function"></a>Функция PreBindAssemblyEx
Возвращает отображаемое имя после применения политики для сборки.  
  
 Эта функция поддерживает .NET Frameworkную инфраструктуру и не предназначена для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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
 окне Определяет контекст приложения.  
  
 `pName`  
 окне Определяет имя сборки.  
  
 `pAsmParent`  
 окне Определяет родительскую сборку. Этот параметр не учитывается.  
  
 `pwzRuntimeVersion`  
 окне Определяет версию среды выполнения.  
  
 `ppNamePostPolicy`  
 заполняет Содержит отображаемое имя после применения политики.  
  
 `pvReserved`  
 окне Зарезервировано для будущего расширения. `pvReserved`должен быть пустой ссылкой.  
  
## <a name="remarks"></a>Примечания  
 `ppNamePostPolicy` Выходной параметр задается только в том случае, если функция возвращает значение HRESULT FUSION_E_REF_DEF_MISMATCH. В противном случае он имеет значение null.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок.** Fusion. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции Fusion](fusion-global-static-functions.md)
