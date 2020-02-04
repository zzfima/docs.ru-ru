---
title: Метод ICorDebugProcess2::GetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
ms.openlocfilehash: 015735e1c6c3b6c146f2fca3a9bdc28baeca2f92
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792521"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a>Метод ICorDebugProcess2::GetDesiredNGENCompilerFlags
Возвращает текущие параметры флага компилятора, используемые средой CLR для выбора правильного предварительно скомпилированного (то есть машинного) образа для загрузки в этот процесс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pdwFlags`  
 заполняет Указатель на побитовую комбинацию значений перечисления [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) , которые используются для выбора правильного предварительно скомпилированного изображения для загрузки.  
  
## <a name="remarks"></a>Заметки  
 Используйте метод [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) , чтобы задать флаги, которые среда CLR будет использовать для выбора правильного предварительно скомпилированного изображения для загрузки.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
