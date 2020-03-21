---
title: Метод ICorDebugAppDomain::GetName
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type:
- apiref
ms.openlocfilehash: 45d27fca888bdabedf197525c63dbd03af7ba1ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179089"
---
# <a name="icordebugappdomaingetname-method"></a>Метод ICorDebugAppDomain::GetName
Получает название домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
         WCHAR              szName[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `cchName`  
 [in] Размер массива `szName`. Установите это значение до нуля, чтобы поместить этот метод в режим запроса.  
  
 `pcchName`  
 (ваут) Указатель на размер имени или количество символов фактически `szName`вернулся в . В режиме запроса это значение позволяет вызывающему знать, насколько велик буфер для выделения для имени.  
  
 `szName`  
 (ваут) Массив, в которых хранится имя домена приложения.  
  
## <a name="remarks"></a>Remarks  
 Отладчик вызывает `GetName` метод один раз, чтобы получить размер буфера, необходимого для имени. Отладчик выделяет буфер, а затем вызывает метод во второй раз, чтобы заполнить буфер. Первый вызов, чтобы получить размер имени, называется *режимом запроса.*  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
