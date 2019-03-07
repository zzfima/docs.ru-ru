---
title: Метод ICorDebugEval2::NewParameterizedObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c35baaee13782566c64dd8447c6a034f699b5cd0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479614"
---
# <a name="icordebugeval2newparameterizedobject-method"></a>Метод ICorDebugEval2::NewParameterizedObject
Создает новый объект параметризованного типа и вызывает метод-конструктор объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pConstructor`  
 [in] Указатель на объект ICorDebugFunction, представляющий конструктор для создания экземпляра объекта.  
  
 `nTypeArgs`  
 [in] Передано число аргументов типа.  
  
 `ppTypeArgs`  
 [in] Массив указателей, каждый из которых указывает на объект, представляющий аргумент типа для объекта, экземпляр которого создается ICorDebugType.  
  
 `nArgs`  
 [in] Число аргументов, переданных в конструктор.  
  
 `ppArgs`  
 [in] Массив указателей, каждый из которых указывает ICorDebugValue объект, представляющий значение аргумента, который передается в конструктор.  
  
## <a name="remarks"></a>Примечания  
 Конструктор объекта может занять <xref:System.Type> параметров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
