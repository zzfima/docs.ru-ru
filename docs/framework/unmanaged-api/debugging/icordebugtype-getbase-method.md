---
title: Метод ICorDebugType::GetBase
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: cff527aa7cde6a13667d47d030a0ef7db96ad5ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122337"
---
# <a name="icordebugtypegetbase-method"></a>Метод ICorDebugType::GetBase
Возвращает указатель интерфейса на объект ICorDebugType, представляющий базовый тип, если он существует, типа, представленного этим `ICorDebugType`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pBase`  
 заполняет Указатель на адрес объекта `ICorDebugType`, который представляет базовый тип.  
  
## <a name="remarks"></a>Заметки  
 Поиск базового типа для типа полезен для реализации общих функциональных возможностей отладчика, таких как вывод всех полей объекта или его родительских классов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
