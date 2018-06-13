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
ms.openlocfilehash: f20c24984aadd05139d1a427b75bc65438539ff1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412809"
---
# <a name="icordebugeval2newparameterizedobject-method"></a>Метод ICorDebugEval2::NewParameterizedObject
Создает новый объект параметризованного типа и вызывает метод конструктора объекта.  
  
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
  
#### <a name="parameters"></a>Параметры  
 `pConstructor`  
 [in] Указатель на объект ICorDebugFunction, который представляет конструктор для создания экземпляра объекта.  
  
 `nTypeArgs`  
 [in] Число аргументов типа передано.  
  
 `ppTypeArgs`  
 [in] Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент типа для объекта, экземпляр которого создается.  
  
 `nArgs`  
 [in] Количество аргументов, переданные в конструктор.  
  
 `ppArgs`  
 [in] Массив указателей, каждый из которых указывает на объект ICorDebugValue, представляющее значение аргумента, переданного конструктору.  
  
## <a name="remarks"></a>Примечания  
 Конструктор объекта может занять <xref:System.Type> параметров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
