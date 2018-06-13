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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84f895e749fc8f2520dbce3caf9e6c11fda78a7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405773"
---
# <a name="icordebugappdomaingetname-method"></a>Метод ICorDebugAppDomain::GetName
Возвращает имя домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `cchName`  
 [in] Размер массива `szName`. Это значение равным нулю, чтобы поместить этот метод в режиме запроса.  
  
 `pcchName`  
 [out] Указатель на размер имя или число символов, фактически извлеченных в `szName`. В режиме запроса, это значение позволяет вызывающему объекту определить размер буфера для выделения для имени.  
  
 `szName`  
 [out] Массив, который содержит имя домена приложения.  
  
## <a name="remarks"></a>Примечания  
 Отладчик вызывает `GetName` метод один раз, чтобы получить размер буфера, который необходим для имени. Отладчик выделяет буфер и затем вызывает метод во второй раз для заполнения буфера. Первый вызов для получения размера имени, называется *режим запроса*.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
